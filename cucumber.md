# show me current page

    # feature/my_failing.feature
    When ....
    And show me the page
    Than ...
    
    # feature/step_definitions/custom_steps.rb
    Then /^show me the page$/ do
      show_page
    end

  
# run steps inside within step definitions

```ruby
When(/^I try to add a text field$/) do
  step 'I should see New Field button'
  click_link 'New Field'
  click_button 'Submit'
end
```

# Examples steps

```ruby
Then(/^some step examlpes/) do
  expect(@user.role).to be_admin_for(@tld.id)
  expect(page.all('table#permissions tbody tr').count).to be == 1
  expect(page).to have_content 'Foo Admin'
  expect(page.first('table#applications tbody tr')).to have_content 'fooo'

  
  click_link 'New Permission'
  click_button 'Add permission'

  select 'Admin', :from => 'permission_role'
  select @tld.extension, :from => 'permission_tld_id'
end
```