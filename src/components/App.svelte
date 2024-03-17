<script>
  // Write your JS here, or import other files
  import { onMount } from "svelte";

  var fs = require("fs"),
    RandomForestClassifier =
      require("random-forest-classifier").RandomForestClassifier;
  var rf = new RandomForestClassifier({
    n_estimators: 10,
  });

  onMount(async () => {
    var testdata = [{
    "length":6.3,
    "width":2.5,
    "petal_length":5,
    "petal_width":1.9,
    //"species":"virginica"
  }
];
rf.fit(data, null, "species", function (err, trees) {
    //console.log(JSON.stringify(trees, null, 4));
    var pred = rf.predict(testdata, trees);

    console.log(pred);

    // pred = ["virginica", "setosa"]
  });
  });
</script>

<main>
  <body>
    <h1>Accident Severity Prediction</h1>

    <p>
      POV: you got into a road accident in the UK... How severe is your
      accident?
    </p>
    <p>Play around with the dropdown to find out!</p>
  </body>
</main>

<style>
  body {
    background-color: black;
  }
  h1 {
    color: white;
    text-align: center;
    font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
      "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  }
  p {
    color: white;
    text-align: center;
    font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
      "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  }
</style>
