.. _betterstockpiling01:

##################
Foundations for Better Stockpiling I: Intro to Quantum Stockpiling
##################

You read *Foundations for Better Stockpiling*. The written portion consists of
a 3 volume treatise entitled *Foundations for Better Stockpiling* authored by
*Mechanixm* in the year 2014. The first parts entitled :ref:`Intro to Quantum
Stockpiling <betterstockpiling01>`, concerns the explanation of basic quantum
stockpiles with minecarts. The second parts entitled :ref:`The Five Primary
Stockpiles <betterstockpiling02>` expands the technique into a method for
fortress-wide stockpiling.  The third parts entitled :ref:`Useful Custom
Stockpiles <betterstockpiling03>` exhibits advanced applications of the method.
The writing is full of illustrations yet very lengthy.


Original sources *Mechanixm's Guide to Better Stockpiling*:
:reddit:`Part 1 <2k0zb3>`, :reddit:`Part 2 <2kuvs1>`, :reddit:`Part 3
<2n9p3u>`.

Edited, updated, and expanded by Ramblurr in 2018.

.. contents::

**Stockpiling** is an essential part of Dwarf Fortress, and is an area that can
be improved upon for both veteran and new players alike. There exist simple
guides that explain more complicated aspects of stockpiling, but nothing that
really shows in detail, with pictures, the step by step process to create a
fortress-wide system yourself. This series will try to accomplish that.

The guide is presented in a way that you can follow along and implement it in
your fortress as you work through the guide.




The Quantum Stockpile
=====================

**So what's a Quantum Stockpile and why is using them a good idea?**

From :wiki:`the wiki <Quantum_stockpile>`:

  Quantum Stockpiles (QSPs) allow you to store an infinite number
  of items in a single tile. QSPs can make for super efficient storage, allowing
  more compact fortresses, shorter hauling routes, more efficient manufacturing
  flows, stocktaking at a glance with look (:kbd:`k`) and potentially higher FPS.

  The simplest QSP is created by designating a garbage dump activity zone,
  dumping the items you want to store and then reclaiming them when you are
  ready to use them. If you place this garbage dump on top of an existing
  stockpile, the dumped items will automatically be considered part of the
  stockpile, allowing the use of stockpile links to distribute the items to
  workshops or other stockpiles.

Also, using quantum stockpiles helps alleviate the need to use bins and barrels
for the storage of certain items. If for no other reason, I highly suggest you
learn this stockpiling technique so that you will stop suffering at the hands
of the buggy game code correlated with those two storage containers.

The Minecart Quantum Stockpile
==============================

.. note::
  If you're following along in your own fort, Take a moment to go to
  your Carpenter's Workshop and queue up a bunch of wooden wheelbarrows and
  minecarts so that they are available. In Part 1, you will need at least 6
  available wheelbarrows and 2 minecarts.


The :wiki:`Minecart Stop Quantum Stockpile
<Quantum_stockpile#The_Minecart_Stop>` is my quantum stockpiling technique of
choice for the following reasons:

- Ease of setup
- Ease of understanding
- Scalability
- Customization

For the purposes of this stockpiling guide, we
will not delve deep into the minecart related topics. We will only use the bits
we need for stockpiling. For further education on minecarts, refer to the
Minecart masterclass.

The Minecart Stop Quantum Stockpile (:abbr:`MQS (Minecart Quantum Stockpile)`)
works by taking advantage of the "dump" feature of minecart track stops. A
track stop is simply a construction you can build on the floor and place a
minecart on. A track stop, when being built, can be configured to dump in a
certain direction (N, S, E, W). When a minecart with items is detected on the
stop, the minecart will dump its contents to the single tile in the direction
specified. If this happens multiple times, the contents of that single tile
will stack and a quantum stockpile is formed. In theory this dump tile can have
an unlimited amount of items on it.

The Minecart Quantum Stockpile is the foundation of the Better Stockpiling
Method and will be used extensively throughout this masterclass.

In its simplest terms, the :abbr:`MQS (Minecart Quantum Stockpile)` works like this:

.. code-block:: none

  rrr     r receiving stockpile, usually 2x3 or 4x3
  rrr     S track stop, set to dump south
   S        has a minecart on top of it
   d      d distribution stockpile, 1x1

You have a receiving stockpile that grabs the items you wish to be quantum
stockpiled.

Those items are then placed in to a minecart, sitting on a track stop, that is
set to dump in a certain direction..

You then create a :kbd:`h` auling route detailing which items you want to take from
the receiving stockpile and which minecart to put them in. Once the appropriate
conditions are met, the minecart will be dumped in the direction you have set
and the contents will land on the 1x1 distribution stockpile.

You now only have a 4x3 stockpile footprint which can potentially hold every
item in your fortress. This is an incredibly powerful tool.


Two Simple Variations of the Minecart Quantum Stockpile
=======================================================

We now take the vanilla :abbr:`MQS (Minecart Quantum Stockpile)` and refine in one extra step by splitting them in
to two different varieties:

- Heavy Items
- Light Items

**Why?**  We split them because some items have different weights and affect
the speed of a dwarf while their hauling things around. You might have noticed
a dwarf hauling a stone from your mining layers dozens of z-levels to your
mason workshops above. Sometimes they will spend months or entire seasons
hauling one stone.

These heavier items are moved faster with wheelbarrows. Having a dwarf path to
the stockpile to grab a wheelbarrow, and then go get that item and bring it
back to the stockpile, is usually a much more efficient use of a dwarf's time
than to have him/her hauling a single stone to the stockpile for an entire
season.

For light items, there's no need to use a wheelbarrow as the added weight of
carrying the light hauled item doesn't affect the dwarf's movement speed.
Indeed, using a wheelbarrow might even make the hauling job take longer as the
hauler must first fetch the wheelbarrow and then go to the item's location.

*Don't fret!* You musn't learn the dwarven weight system nor memorize the
weights of every item. Simple remember this short list of **heavy items**:

- Stones
- All furniture
- Metal and Wooden Empty Cages
- Corpses of humanoid and larger sizes

These items will only be assigned to your Heavy Items :abbr:`MQS (Minecart Quantum Stockpile)`. All other items can
be assigned to the Light Items :abbr:`MQS (Minecart Quantum Stockpile)` (with some notable exceptions, such as food,
continue onward for these exceptions).


Example 1: Creating a Heavy Items Minecart Quantum Stockpile
==========================================================

For this example, we will start out with a stockpile I've created that is
grabbing Wood and Stones from anywhere on the map.

.. figure:: images/stockpile1-1.png

   Our Example Stockpile of stone and wood

.. figure:: images/stockpile1-2.png

   Example Stockpile Settings

In reality, when you go to setup your Minecart Quantum Stockpiles for your
Primary Materials Stockpiles (which are discussed in Part 2 of this
masterclass) your Minecart Quantum Stockpile receiver stockpiles will be ones
set to take from anywhere on the map, as opposed to this example where the
receiver stockpiles are set to take from links.


1. Prepare a Heavy Items :abbr:`MQS (Minecart Quantum Stockpile)` for Stone
------------------------------------------

.. figure:: images/stockpile1-3.png

   Designating the stockpiles for a heavy item MQS.

a) Create two 2x3 Receiver Stone Stockpiles directly north-south of
   eachother using :kbd:`p`, :kbd:`s`
b) Skip a single space south and create a 1x1 Stone Stockpile. This 1x1
   Stockpile is what will become your Quantum Stockpile. Press :kbd:`ESC` to close
   out the Stockpile Menu.
c) Press :kbd:`b`, :kbd:`C`, :kbd:`S` to open the Track Stop Menu. Move
   your cursor to the empty middle space between your Receiver Stockpiles and
   Quantum Stockpiles. The Track Stop needs to be right next to your Quantum
   Stockpile, so it can dump into it. The Track Stop *does not* have to be
   adjacent to the Receiver Stockpile.  Press :kbd:`d` twice to change the
   dump direction to :guilabel:`South` before pressing :kbd:`Enter` to place
   the Track Stop.
d) Press :kbd:`ESC` twice to get back to the main menu.
e) :kbd:`q` uery over your two Receiver Stockpiles and press :kbd:`w`  until you have 3 Wheelbarrows set for each
f) :kbd:`q` uery over your Quantum Stockpile, and set Wheelbarrows to 0


.. figure:: images/stockpile1-4.gif

   A Mechanic will build the Trackstop. Dwarves deliver the Wheelbarrows

**For the sake of this example**, we will change the settings of our Receiver Stone Stockpiles
to take from that example Stockpile we created that is grabbing Stones and
Wood. Once we make these changes, the dwarves will start hauling items to the
Receiver Stockpiles and stop once they are full of Stones.

g) :kbd:`q` uery over the two Receiver Stockpiles and press :kbd:`t` to take from links and target the Example Stockpile. Press :kbd:`ESC` when done.

.. figure:: images/stockpile1-5.gif

  Making the Receiver Stone Stockpiles take from our Example stockpile. This
  step is for this example only. Usually these receiver stockpiles will take
  from anywhere.


.. tip:: Why use two 2x3 Receiver Stockpiles?

  We use the 2x3 size for the Heavy Item Receiver Stockpiles to accommodate the
  use of wheelbarrows. You can only use 3 Wheelbarrows per stockpile, no matter
  the size of the stockpile. Furthermore, a stockpile will not generate more
  hauling jobs than wheelbarrows that exist.

  So if you have a single 4x3 stockpile, for a total of 12 spaces, you will
  still only generate 3 hauling jobs at a time. 

  But by using two 2x3 stockpiles with wheelbarrows, we still have 12 spaces
  total, but can have up to 6 hailing jobs generated at a time.

2. Create the Stone Hauling Route
---------------------------------

.. figure:: images/stockpile1-6.gif

  Creating the stone hauling route. Steps outlined below.

a) Press :kbd:`h`  to bring up the Hauling Routes Menu
b) Move your cursor and place it directly over your Track Stop. Press :kbd:`r`  to create a new Route
c) Press :kbd:`n`  to name it. (For this example, type in :guilabel:`StoneExample` and press :kbd:`Enter` when done)
d) With the cursor still directly over the Track Stop, press :kbd:`s`  to create a new Stop
e) Press :kbd:`Enter` to define the Stop Settings
f) Press :kbd:`x`  three times to remove the three default Guide conditions
g) Press :kbd:`Enter` to define what items you want to be placed in to this Minecart. This should match the Stockpile settings you have setup on your Receiver Stockpiles. In this example, our Receiver Stockpiles are just all Stones. So, scroll down and press :kbd:`e`  on Stone to enable it. Press :kbd:`ESC` when you're done
h) You now need to choose the Receiver Stockpiles that you want to grab the Stones from to be placed in the Minecart. Move your cursor up one space, to the nearest Receiver Stockpile, and then Press :kbd:`s` . You will see a new :guilabel:`Take From Stone Stockpile` entry at the upper right
i) Move your cursor up to the top Receiver Stockpile and Press :kbd:`s`  again. You will now see the two different :guilabel:`Take From Stone Stockpile` entries at the upper right
j) Press :kbd:`ESC` once you are done selecting to :guilabel:`Take From` your Receiver Stockpiles
k) You will now be at the Hauling Menu, and you will see your StoneExample Hauling route and the one Stop associated with it. With the :guilabel:`Stop 1` highlighted, press :kbd:`v`  to choose a minecart. The quality or material of the minecart is irrelevant for general hauling. Select whichever minecart you want to use by highlighting it and pressing :kbd:`Enter` to assign the vehicle
l) Press :kbd:`ESC` to exit the Hauling menu

.. figure:: images/stockpile1-7.gif

  Unpause the game and a dwarf will come and place the Minecart for your newly
  created Hauling Route. Once that is done, all dwarves enabled for Stone Hauling
  will start placing Stone in to the Minecart and then dumping it on to
  the 1x1 Stone Stockpile, while at the same time continuing to re-populate the
  Receiver Stockpile.

.. figure:: images/stockpile1-8.gif

  Let's take a look at the Contents of our Stone Quantum Stockpile.

If you've set everything up correctly, you should be the proud owner of a Stone
Quantum Stockpile.  The initial Example Stockpile will soon be emptied of
stones and be left with only wood logs.

Example 2: Creating a Light Items Minecart Quantum Stockpile
============================================================

For this example, we will be using the same wood and stones Example Stockpile
created in Example 1.

We will create a Light Items Wood Quantum Stockpile to haul away the wood logs
into a MQS.

Creating a Light Items Minecart Quantum Stockpile follows the same steps as
creating a Heavy Items MQS.

1. Prepare a Light :abbr:`MQS (Minecart Quantum Stockpile)` for Wood
-------------------------------

.. figure:: images/stockpile1-9.gif

a) Create a 4x3 Wood Stockpile with :kbd:`p`, :kbd:`w`.  This will be your Receiver Stockpile.
b) Skip a space for where you will build your Track Stop and create a 1x1 Wood Stockpile. This will be your Quantum Stockpile. Press :kbd:`ESC` when done.
c) :kbd:`q` uery over your two Stockpiles and press :kbd:`w`  until you have 0 Wheelbarrows set for each. **Remember:** we do not want to use Wheelbarrows for light items.
d) Press :kbd:`t`  to take from links and target the Example Stockpile. Press :kbd:`ESC` when done.
e) Press :kbd:`b`, :kbd:`C`, :kbd:`S` to open the Track Stop Menu. Move your cursor to the empty middle space between your Receiver Stockpiles and Quantum Stockpiles. The Track Stop needs to be right next to your Quantum Stockpile. It *does not* have to be adjacent to the Receiver Stockpile. Press :kbd:`d`  twice to change the dump direction to South before pressing :kbd:`Enter` to place the Track Stop.
f) Select your build material and press :kbd:`Enter` to build the Tack Stop. Press :kbd:`ESC` twice to get back to the main menu.

.. tip::
  **Why 4x3?**

  Because 12 simultaneous Wood Log hauling jobs is reasonable to me, and its size
  also matches up exactly with the 2 2x3 Heavy Items Receiver Stockpiles. Feel
  free to use whatever size Receiver Stockpile you wish, and as *many* Receiver
  Stockpiles as you wish.

.. figure:: images/stockpile1-10.gif

  A Mechanic will build the Track Stop and your Wood Haulers fill the Receiver Stockpile



2. Create the Wood Hauling Route
--------------------------------

.. figure:: images/stockpile1-11.gif

  Creating the wood hauling route. Steps outlined below.

a) Press :kbd:`h`  to bring up the Hauling Routes Menu
b) Move your cursor and place it directly over your Track Stop. Press :kbd:`r`  to create a new Route.
c) Press :kbd:`n`  to name it. (For this example, type in :guilabel:`WoodExample` and press :kbd:`Enter` when done)
d) With the cursor still directly over the Track Stop, press :kbd:`s`  to create a new Stop
e) Press :kbd:`Enter` to define the Stop Settings
f) Press :kbd:`x`  three times to remove the three default guide conditions
g) Press :kbd:`Enter` to define what items you want to be placed in to this Minecart. This should match the Stockpile settings you have setup on your Receiver Stockpiles. In this example, our Receiver Stockpiles are Wood Logs. So, scroll down and press :kbd:`e` on Wood to enable it. Press :kbd:`ESC` when you're done.
h) You now need to choose the Receiver Stockpile that you want to grab the Wood from to be placed in the Minecart. Move your cursor up one space, to the Receiver Stockpile, and then Press :kbd:`s` . You will see a new :guilabel:`Take From Wood Stockpile` entry at the upper right
i) Press :kbd:`ESC` once you are done selecting to :guilabel:`Take From` your Receiver Stockpile
j) You will now be at the Hauling Menu, and you will see your WoodExample Hauling route and the one Stop associated with it. With the :guilabel:`Stop 1` highlighted, press :kbd:`v`  to choose a minecart. The quality or material of the minecart is irrelevant for general hauling. Select whichever minecart you want to use by highlighting it and pressing :kbd:`Enter` to assign the vehicle
k) Press :kbd:`ESC` to exit the Hauling menu

.. figure:: images/stockpile1-12.gif

  A Dwarf will place the Minecart for your Wood Hauling Route. Once done, Dwarves enabled for Wood Hauling will come and place Wood in the Minecart and then dump it on to the 1x1 Stone Stockpile

.. figure:: images/stockpile1-13.gif

  Let's take a look at our Wood Quantum Stockpile after having let the game run for a bit.

If you've set everything up correctly, you should be the proud owner of a Wood
Logs Minecart Quantum Stockpile.


Name Your Quantum Stockpiles Using DFHack
=======================================================

Since you'll probably be using these stockpiles to feed other stockpiles and
workshops, let's give them some proper names.



.. figure:: images/stockpile1-14.gif


a) Press :kbd:`q`  and highlight your Stone Quantum Stockpile
b) Press :kbd:`Ctrl` + :kbd:`Shift` + :kbd:`n` to bring up the name screen.
c) Type in a Name for your Stone Quantum Stockpile and then press :kbd:`Enter`
d) Move your :kbd:`q`  cursor over to your Wood Quantum Stockpile
e) Press :kbd:`Ctrl` + :kbd:`Shift` + :kbd:`n` to bring up the name screen.
f) Type in a Name for your Wood Quantum Stockpile and then press :kbd:`Enter`

You should now be able to see that the stockpile names have changed at the top
right of the screen.

*Why do you want to name your stockpiles?* To be able to see where
things are being hauled.

Here is a real-life example of named stockpiles in use:


.. figure:: images/stockpile1-15.gif

.. figure::  images/stockpile1-16.gif

  By renaming a Wood Quantum Stockpile Feeder and then using the jobs menu
  :kbd:`j`, you can see *WHO* is hauling what and *WHERE* exactly they are
  hauling it.


Continue to Part II :ref:`The Five Primary Stockpiles <betterstockpiling02>`
