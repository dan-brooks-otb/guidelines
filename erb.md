
# Coding standards for ERB / HTML

## HTML

### Indentation

Indent all erb & HTML with two spaces:

*The right way:*

```erb
<div class="flight-information-board">
  <div class="flight-information-board__info">
    <% [flight.outbound, flight.inbound].each do |journey| %>
      <div class="flight-information-board__section">
        <span class="flight-information-board__label flight-information-board__label--emphasis">
          <%= journey.departure_time %>
        </span>
        <span class="flight-information-board__label">
          <%= journey.departure_airport_name %>
        </span>
      </div>
    <% end %>
  </div>
</div>
```

*The wrong way:*

```erb
<div class="flight-information-board">
    <div class="flight-information-board__info">
        <% [flight.outbound, flight.inbound].each do |journey| %>
            <div class="flight-information-board__section">
                <span class="flight-information-board__label flight-information-board__label--emphasis">
                    <%= journey.departure_time %>
                </span>
                <span class="flight-information-board__label">
                    <%= journey.departure_airport_name %>
                </span>
            </div>
        <% end %>
    </div>
</div>
```
### Quotemarks

Prefer double quotes for HTML attributes.
Anything inside an `erb` tag is Ruby so should use single quotes by default, double quotes for interpolation.

### HTML5

Make use HTML5 tags where appropriate, e.g. `<header>` or `<input type="email">`. Please see [HTML5 Doctor](http://html5doctor.com/) for more information about HTML5.

### Grid classes

Where possible, divs that use grid classes (e.g. `row` or `column-(n)`) should not have any additional classes applied to them. However on occasion it is unavoidable, for example if using flexbox to overwrite grid functionality on smaller screen sizes.

For example,

#### Bad

```
<div class="column-6 flight-info">
  ...
</div>
```

#### Good

```
<div class="column-6">
  <div class="flight-info">
    ...
  </div>
</div>
```

### Text elements

Text elements such as headings and paragraphs should have the opening and closing tags on the same line, with the text content between them, e.g.

```
<p>Some text goes here</p>
```

## Templating

### Wrapping

When wrapping a Ruby statment across multiple lines, keep the method name on the same line as the opening erb tag and keep each method argument on its own line:

*The right way:*

```erb
<%= render(
  'components/banner_message',
  banner_link: t('contact.emergency.url'),
  banner_logo: nil,
  message: t('contact.emergency.message'),
  cta: true
) %>
```

*The wrong way:*

```erb
<%=
  render('components/banner_message',
    banner_link: t('contact.emergency.url'),
    banner_logo: nil,
    message: t('contact.emergency.message'),
    cta: true
  )
%>
```
