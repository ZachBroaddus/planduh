<!DOCTYPE html>
<html lang="en">
  <head>
    <title>PlanDuh</title>

    <%= csrf_meta_tags %>

    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <%= stylesheet_link_tag    'application',  media: 'all' %>
    <%= javascript_include_tag  'application' %>
  </head>


  <body cz-shortcut-listen="true">

    <div class="container">

    <nav class="navbar navbar-expand-md navbar-dark bg-dark">
      <a class="navbar-brand" href="#">PlanDuh</a>
      <button class="navbar-toggler collapsed" type="button" data-toggle="collapse" data-target="#navbarsExample04" aria-controls="navbarsExample04" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="navbar-collapse collapse" id="navbarsExample04" style="">
        <ul class="navbar-nav ml-auto">
          <% if logged_in? %>

<!--           <li class="nav-item active">
            <a class="nav-link" href="http://localhost:3000/">Home <span class="sr-only">(current)</span></a>
          </li> -->

          <li class="nav-item active"><%= link_to "#{current_user.first_name}'s Profile", user_path(current_user.id), class: "nav-link"  %></li>

          <li class="nav-item active"><%= link_to "Logout", logout_path, class: "nav-link" %></li>

          <% else %>
          <li class="nav-item active"><%= link_to "Home", root_path, class: "nav-link"  %></li>

          <li class="nav-item active"><%= link_to "Register", new_user_path, class: "nav-link" %></li>

          <li class="nav-item active"><%= link_to "Login", new_session_path, class: "nav-link" %></li>
          <% end %>
        </ul>

      </div>
    </nav>

    <!-- <h3 class="text-muted">PlanDuh</h3> -->

    <main role="main">

      <div class="jumbotron">
        <center>
          <img src='https://i.imgur.com/W29FmAv.png' width="150px" />
          <!-- <h2>PlanDuh</h2> -->
          <% if logged_in? %>
            <p>"Oh, I don't know what to do." <br/>- <span><%= current_user.first_name %></span> before PlanDuh</p>
            <p>"I had a lot of fun." <br />- <span><%= current_user.first_name %></span> after PlanDuh</p>
          <% else %>
            <p>"Oh, I don't know what to do." <br/>- person before PlanDuh</p>
            <p>"I had a lot of fun." <br />- person after PlanDuh</p>
          <% end %>
          <!-- <p class="lead">Discover Local Events </p> -->
          <!-- <p><a class="btn btn-lg btn-success" href="#" role="button">Learn More</a></p></center> -->
      </div>


      <% flash.each do |name, msg| %>
        <%= content_tag(:div, msg, class: "alert") %>

      <% end  %>

        <%= yield %>

    </main>

  <footer class="footer">
    <p>© Adam, Zach, Mitch, Kalier & Nicole PlanDuh Company 2017</p>
  </footer>

</div> <!-- /container -->


</body>


</html>
