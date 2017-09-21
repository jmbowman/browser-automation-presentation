.. Web Browser Automation presentation master file, created by
   sphinx-quickstart on Mon Jul 17 11:37:43 2017.

======================
Web Browser Automation
======================

.. revealjs:: Web Browser Automation
 :subtitle: Interacting with Rendered Web Pages for Tests and More
 :data-transition: slide
 :title-heading: h3
 :subtitle-heading: h4

 | Jeremy Bowman
 | jbowman@edx.org

.. revealjs:: Why Automate a Browser?
 :data-transition: slide
 :title-heading: h3

 * Verify in-browser JavaScript
 * Check for breakage of core functionality
 * Confirm compatibility with supported browsers

.. revealjs:: When Not to Automate a Browser
 :data-transition: slide
 :title-heading: h3

 * Unit tests
 * Rendered markup tests
 * Data retrieval or web scraping

.. revealjs:: How to Automate a Browser
 :data-transition: slide
 :title-heading: h3

 * Selenium
 * W3C WebDriver API
 * Custom headless browser (PhantomJS, CasperJS, SlimerJS, etc.)

.. revealjs:: What Is Selenium?
 :data-transition: slide
 :title-heading: h3

 * Browser automation API
 * Java server for controlling 1+ browsers
 * Client libraries for working with both of the above

.. revealjs:: 1: Directly Drive a Local Browser
 :data-transition: slide
 :title-heading: h3

 * Firefox 47 and earlier
 * Safari

 .. blockdiag::
   :align: center
 
   diagram {
     "Test Case" -> "Browser Extension";
     "Rendering Engine" -> "Web Application";
     group {
       label = "Test Container";
       "Test Case";
       group {
         label = "Browser";
         color = "#000000";
         shape = line;
         style = dashed;
         "Browser Extension" -> "Rendering Engine"
       }
     }
     group {
       label = "Web Server";
       "Web Application";
     }
   }

.. revealjs:: 2: Use a Local Binary Driver
 :data-transition: slide
 :title-heading: h3

 * Chrome
 * Firefox 47+

 .. blockdiag::
   :align: center
 
   diagram {
     "Browser" -> "Web Application";
     group {
       label = "Test Container";
       "Test Case" -> "Driver Binary" -> "Browser";
     }
     group {
       label = "Web Server";
       "Web Application";
     }
   }

.. revealjs:: 3: Drive a Remote Browser
 :data-transition: slide
 :title-heading: h3

 .. blockdiag::
   :align: center
 
   diagram {
     "Test Case" -> "Selenium Server";
     "Browser" -> "Web Application";
     group {
       label = "Test Container";
       "Test Case";
     }
     group {
       label = "Selenium Container";
       "Selenium Server" -> "Driver Binary" -> "Browser";
     }
     group {
       label = "Web Server";
       "Web Application";
     }
   }

.. revealjs:: Which Operations Can Be Automated?
 :data-transition: slide
 :title-heading: h3

 * Load a URL
 * Find an element
 * Get an element's attributes
 * Click an element
 * Run a script
 * ...

.. revealjs:: Why Not Just Use Selenium Directly?
 :data-transition: slide
 :title-heading: h3

 * Low level operations
 * API not a good match for reliable tests
 * A minor change in site behavior can impact many tests

.. revealjs:: Layers Above Selenium
 :data-transition: slide
 :title-heading: h3

 * bok-choy (acceptance tests)
 * lettuce (other acceptance tests)
 * karma + jasmine (JS unit tests)
 * pa11ycrawler (a11y audits)
 
.. revealjs:: Thank you!
 :data-transition: slide
 :title-heading: h3

 Questions?

 .. rv_small::

  | Jeremy Bowman
  | jbowman@edx.org
