# rest_web_services
copyright belong to Pragmatic BookShelf:
#---
# Excerpted from "The Cucumber Book",
# published by The Pragmatic Bookshelf.
# Copyrights apply to this code. It may not be used to create training material, 
# courses, books, articles, and the like. Contact us if you are in doubt.
# We make no guarantees that this code is fit for any purpose. 
# Visit http://www.pragmaticprogrammer.com/titles/hwcuc for more book information.
#---
# This file should contain all the record creation needed to seed the database with its default values.
# The data can then be loaded with the rake db:seed (or created alongside the db with db:setup).
#
This is just a hands-on for cucumber with rack/test
Feature: Fruit list
  In order to make a great smoothie
  I need some fruit.

  Scenario: List fruit                                # features/fruit_list.feature:5
    Given the system knows about the following fruit: # features/step_definitions/rest_steps.rb:1
      | name       | color  |
      | banana     | yellow |
      | strawberry | red    |
    When the client requests GET /fruits              # features/step_definitions/rest_steps.rb:4
    Then the response should be JSON:                 # features/step_definitions/rest_steps.rb:8
      """
      [
        {"name": "banana", "color": "yellow"},
        {"name": "strawberry", "color": "red"}
      ]
      """

1 scenario (1 passed)
3 steps (3 passed)
0m0.143s
