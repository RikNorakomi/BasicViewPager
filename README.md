# BasicViewPager
This is a exaple of how to create a basic viewPager


Excerpt from: http://www.javacodegeeks.com/2013/04/android-tutorial-using-the-viewpager.html

 * Using the ViewPager requires some knowledge of both Fragments and PageAdapters
* You can think of PageAdapters in the same way that you think of ListAdapters. The Page Adapter’s job is to supply Fragments (instead of views) to the UI for drawing.

### Implementing the activity with viewpager:
*The class inherits from FragmentActivity, not Activity
 * The activity has a pageAdapter object ad a fragment(s) object which  needs to be passed to the pageAdapter
* the activity needs to initialize it's own pageadapter


### Implementing the PageAdapter
* we crete a pageadapter class that inherits from FragmentPageAdapter & then:
* make sure the adapter has our fragment list (passed to constructor from activity)
* make sure it gives the activity the correct fragment`

### Now we only need to set up the fragments. For this we need to do 2 things:
* set up a getFragment() in the PageViewActivity
* create a MyFragment class: The MyFragment class also has it’s own layout file. For this example, the layout file only consists of a simple TextView. 

For the fragment code:
* The trick is to use a static (final) constructor like in a singleton and use a bundle to pass in specific information for each different fragment


# NB. For More Advance Developers
There are actually a few different types of FragmentPageAdapters out there. 
It is important to know what they are and what they do, as knowing this bit of information could save you some 
time when creating complex applications with the ViewPager. The FragmentPagerAdapter is the more general PageAdapter 
to use. This version does not destroy Fragments it has as long as the user can potentially go back to that Fragment. 
The idea is that this PageAdapter is used for mainly “static” or unchanging Fragments. If you have Fragments that are 
more dynamic and change frequently, you may want to look into the FragmentStatePagerAdapter. This Adapter is a bit more 
friendly to dynamic Fragments and doesn’t consume nearly as much memory as the FragmentPagerAdapter.
