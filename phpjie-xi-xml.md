#### 待解析XML：

&lt;?xml version="1.0" encoding="utf-8"?&gt;

&lt;menu&gt;

```
&lt;items name="Pizzas"&gt;

   &lt;taste&gt;

      &lt;name&gt;Tomato&lt;/name&gt;

      &lt;large&gt;9.75&lt;/large&gt;

      &lt;small&gt;5.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

       &lt;name&gt;Onions&lt;/name&gt;

       &lt;large&gt;10.85&lt;/large&gt;

       &lt;small&gt;6.85&lt;/small&gt;

   &lt;/taste&gt;

    &lt;taste&gt;

       &lt;name&gt;Peppers&lt;/name&gt;

       &lt;large&gt;10.85&lt;/large&gt;

       &lt;small&gt;6.85&lt;/small&gt;

   &lt;/taste&gt;

    &lt;taste&gt;

       &lt;name&gt;Broccoli&lt;/name&gt;

       &lt;large&gt;10.85&lt;/large&gt;

       &lt;small&gt;6.85&lt;/small&gt;

   &lt;/taste&gt;

&lt;/items&gt;

&lt;items name="Salads"&gt;

   &lt;taste&gt;

      &lt;name&gt;Garden&lt;/name&gt;

      &lt;large&gt;5.75&lt;/large&gt;

      &lt;small&gt;3.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

       &lt;name&gt;Greek&lt;/name&gt;

       &lt;large&gt;8.50&lt;/large&gt;

       &lt;small&gt;5.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

       &lt;name&gt;Antipasto&lt;/name&gt;

       &lt;large&gt;4.50&lt;/large&gt;

       &lt;small&gt;2.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

       &lt;name&gt;Chef&lt;/name&gt;

       &lt;large&gt;10.50&lt;/large&gt;

       &lt;small&gt;5.50&lt;/small&gt;

   &lt;/taste&gt;    

&lt;/items&gt;

&lt;items name="Grinders"&gt;

   &lt;taste&gt;

      &lt;name&gt;Meatless&lt;/name&gt;

      &lt;large&gt;4.95&lt;/large&gt;

      &lt;small&gt;2.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;Hamburger&lt;/name&gt;

      &lt;large&gt;14.95&lt;/large&gt;

      &lt;small&gt;3.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;Meatball&lt;/name&gt;

      &lt;large&gt;11.50&lt;/large&gt;

      &lt;small&gt;4.50&lt;/small&gt;

   &lt;/taste&gt;

&lt;/items&gt;

&lt;items name="Spaghetti or ziti"&gt;

   &lt;taste&gt;

      &lt;name&gt;With Sauce&lt;/name&gt;

      &lt;large&gt;5.40&lt;/large&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;With Sausage&lt;/name&gt;

      &lt;large&gt;6.45&lt;/large&gt;

   &lt;/taste&gt;

&lt;/items&gt;

&lt;items name="Homemade calzones"&gt;

   &lt;taste&gt;

      &lt;name&gt;Italian&lt;/name&gt;

      &lt;large&gt;15.75&lt;/large&gt;

      &lt;small&gt;4.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;Chinese&lt;/name&gt;

      &lt;large&gt;9.75&lt;/large&gt;

      &lt;small&gt;4.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;Genon&lt;/name&gt;

      &lt;large&gt;6.75&lt;/large&gt;

      &lt;small&gt;3.50&lt;/small&gt;

   &lt;/taste&gt;

   &lt;taste&gt;

      &lt;name&gt;Ham&lt;/name&gt;

      &lt;large&gt;5.75&lt;/large&gt;

      &lt;small&gt;4.50&lt;/small&gt;

   &lt;/taste&gt;

&lt;/items&gt;
```

&lt;/menu&gt;

#### PHP解析代码：

&lt;?php

```
  $xml=simplexml\_load\_file\('../etc/menu.xml'\);

  foreach\($xml-&gt;children\(\) as $items\){

      echo $items-&gt;attributes\(\)-&gt;name.'&lt;br&gt;';

      foreach\($items-&gt;children\(\) as $taste\){

          echo $taste-&gt;name.'&nbsp;&nbsp;&nbsp;';

          echo $taste-&gt;large.'&nbsp;&nbsp;&nbsp;';

          echo $taste-&gt;small.'&nbsp;&nbsp;&nbsp;';

          echo '&lt;br&gt;';

          }

      }
```

?&gt;

