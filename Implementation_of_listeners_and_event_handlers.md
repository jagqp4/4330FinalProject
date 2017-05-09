# Java Implementation of Listeners, and Event Handlers
* The EventHandler class provides support for dynamically generating event listeners whose methods execute a simple statement involving an incoming event object and a target object.
* The EventHandler class is intended to be used by interactive tools, such as application builders, that allow developers to make connections between beans.
* Typically connections are made from a user interface bean (the event source) to an application logic bean (the target).

#### Code Example:
* The simplest use of EventHandler is to install a listener that calls a method on the target object with no arguments.
* In the following example we create an ActionListener that invokes the toFront method on an instance of javax.swing.JFrame.

myButton.addActionListener(
    (ActionListener)EventHandler.create(ActionListener.class, frame, "toFront"));
When myButton is pressed, the statement frame.toFront() will be executed. One could get the same effect, with some additional compile-time type safety, by defining a new implementation of the ActionListener interface and adding an instance of it to the button:
//Equivalent code using an inner class instead of EventHandler.
myButton.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        frame.toFront();
    }
});

# C# Implementation of Listeners, and Event Handlers
* An event in C# is a way for a class to provide notifications to clients of that class when some interesting thing happens to an object.
* The most familiar use for events is in graphical user interfaces; typically, the classes that represent controls in the interface have events that are notified when the user does something to the control (for example, click a button).
* Events, however, need not be used only for graphical interfaces. Events provide a generally useful way for objects to signal state changes that may be useful to clients of that object. Events are an important building block for creating classes that can be reused in a large number of different programs.

#### Code Example using the C# EventHandler delegate type:

// events2.cs
using System;
namespace MyCollections
{
   using System.Collections;

   // A class that works just like ArrayList, but sends event
   // notifications whenever the list changes:
   public class ListWithChangedEvent: ArrayList
   {
      // An event that clients can use to be notified whenever the
      // elements of the list change:
      public event EventHandler Changed;

      // Invoke the Changed event; called whenever list changes:
      protected virtual void OnChanged(EventArgs e)
      {
         if (Changed != null)
            Changed(this,e);
      }

      // Override some of the methods that can change the list;
      // invoke event after each:
      public override int Add(object value)
      {
         int i = base.Add(value);
         OnChanged(EventArgs.Empty);
         return i;
      }

      public override void Clear()
      {
         base.Clear();
         OnChanged(EventArgs.Empty);
      }

      public override object this[int index]
      {
         set
         {
            base[index] = value;
            OnChanged(EventArgs.Empty);
         }
      }
   }
}

namespace TestEvents
{
   using MyCollections;

   class EventListener
   {
      private ListWithChangedEvent List;

      public EventListener(ListWithChangedEvent list)
      {
         List = list;
         // Add "ListChanged" to the Changed event on "List":
         List.Changed += new EventHandler(ListChanged);
      }

      // This will be called whenever the list changes:
      private void ListChanged(object sender, EventArgs e)
      {
         Console.WriteLine("This is called when the event fires.");
      }

      public void Detach()
      {
         // Detach the event and delete the list:
         List.Changed -= new EventHandler(ListChanged);
         List = null;
      }
   }

   class Test
   {
      // Test the ListWithChangedEvent class:
      public static void Main()
      {
      // Create a new list:
      ListWithChangedEvent list = new ListWithChangedEvent();

      // Create a class that listens to the list's change event:
      EventListener listener = new EventListener(list);

      // Add and remove items from the list:
      list.Add("item 1");
      list.Clear();
      listener.Detach();
      }
   }
}
