<div class="container">


<div id="exampleAccordion" data-children=".item">

  <div class="item">
    <ul list-style-type: none;>
    <% @activities.each do |activity| %>
        <% if activity.version == "event" %>
    <a data-toggle="collapse" data-parent="#exampleAccordion" href="#exampleAccordion2" aria-expanded="false" aria-controls="exampleAccordion2">
      <p> We found <%= @activities.length%> activities for <%= activity.format_date %>
    </a>
    <div id="exampleAccordion2" class="collapse" role="tabpanel">
      <p class="mb-3">

       <%= image_tag(activity.image_url, size: "320x240") %>
        <li>Event: <%= activity.name %> </li>
        <li>Address: <%= activity.display_address %></li>
        <li>Date: <%= activity.format_date %></li>
        <li>Time: <%= activity.format_time %></li>
        <li><%= link_to "Visit Event Site", activity.event_site_url %></li>
        <li><%= link_to "Buy Tickets", activity.tickets_url if activity.is_free == false %></li>
        <li>Cost: $<%= activity.filter_cost %></li><br>
        <% else %>
        <%= image_tag(activity.image_url, size: "320x240") %>
        <li>Event: <%= activity.name %> </li>
        <li>Address: <%= activity.display_address %></li>
        <li>Phone: <%= activity.display_phone %></li>
        <li>Rating: <%= activity.rating %></li>
        <li>Price: <%= activity.price %></li>
        <li>Type: <%= activity.title %></li>
        <li><%= link_to "Visit Website", activity.url %></li>
         <% end %>


<!-- <div id="googleMap" style="width: 400px; height: 400px"></div>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDrLYL2C-ffJ7nncDl6Sb4QzM6Irt5yRXc&callback=myMap"></script>
</p>
</div> -->


<!-- Modal Overlay for Save and Maybe -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#showModal" data-whatever="save">Save</button>
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#showModal" data-whatever="maybe">Maybe</button>
<button type="button" class="btn btn-primary" >Try Again</button>

<div class="modal fade" id="showModal" tabindex="-1" role="dialog" aria-labelledby="showModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="showModalLabel">Save Itinerary</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form>
          <div class="form-group">
            <label for="itinerary-name" class="col-form-label">Itinerary Name:</label>
            <input type="text" name="itinerary_name" class="form-control" id="itinerary-name">
          </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary m-save">Save</button>
      </div>
    </div>
  </div>
</div>


      </p>
      <% end %>
    </ul>
    </div>
  </div>

</div>
</div>