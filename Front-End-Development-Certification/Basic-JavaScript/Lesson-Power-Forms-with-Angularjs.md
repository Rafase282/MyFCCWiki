# Forms

```html
<li ng-repeat="review in product.reviews">
                <blockquote>
                  <strong> {{review.stars}} Stars </strong>
                  {{review.body}}
                  <cite class="clearfix">— {{review.author}}</cite>
                </blockquote>
              </li>
```

# Create A Review Form

```html
<form name="reviewForm">
  <!--  Live Preview -->
  <blockquote>
    <strong> Stars</strong>

    <cite class="clearfix">—</cite>
  </blockquote>

  <!--  Review Form -->
  <h4>Submit a Review</h4>
  <fieldset class="form-group">
    <select ng-model="review.stars" class="form-control" ng-options="stars for stars in [5,4,3,2,1]"  title="Stars">
      <option value="">Rate the Product</option>
    </select>
  </fieldset>
  <fieldset class="form-group">
    <textarea ng-model="review.body" class="form-control" placeholder="Write a short review of the product..." title="Review"></textarea>
  </fieldset>
  <fieldset class="form-group">
    <input ng-model="review.author" type="email" class="form-control" placeholder="jimmyDean@example.org" title="Email" />
  </fieldset>
  <fieldset class="form-group">
    <input type="submit" class="btn btn-primary pull-right" value="Submit Review" />
  </fieldset>
</form>
```
