# C-Sharp-Live-Project
My C# live project for The Tech Academy's Software Developer Bootcamp

# Rental History Pages (ASP.NET MVC) - Code Summary

This project focused on building and improving the Rental History pages of an ASP.NET MVC application. The goal was to practice working with models, Razor views, and basic front-end behavior while following the MVC pattern.

I created a RentalHistory model to store rental information, including the rental name, whether the rental was damaged, and a field for damage details or general notes. The Create and Edit pages were styled to improve usability by aligning labels and inputs on the same line, limiting the form width, and centering the action buttons for a cleaner layout.

JavaScript was added to improve the user experience by dynamically changing the meaning of the damage field. When a rental is marked as damaged, the “Damages Incurred” field is used. When it is not damaged, the same field is used for notes. This helps ensure the form clearly reflects the type of information being entered.

Overall, this project helped reinforce core concepts such as MVC architecture, model binding, Razor syntax, and simple JavaScript for interactive UI behavior.

# RentalHistory Model

The RentalHistory model stores rental information, damage status, and damage notes or general notes, depending on the rental condition:

```csharp
public class RentalHistory
{
    public int RentalHistoryId { get; set; }
    public bool RentalDamaged { get; set; }
    public string DamagesIncurred { get; set; }
    public string Rental { get; set; }
}
```

# Create & Edit Page Layout Improvements

The Create and Edit forms were styled to improve usability:

Form width restricted to ~600px

Labels and inputs placed on the same line

Buttons are centered and placed inside the form

```csharp
<div class="form-group row">
    <label class="col-md-4 col-form-label">Rental</label>
    <div class="col-md-8">
        @Html.TextBoxFor(m => m.Rental, new { @class = "form-control" })
    </div>
</div>
```

# JavaScript: Damages vs Notes Behavior

JavaScript was added so the DamagesIncurred field dynamically represents damage details or general notes, depending on whether the rental was damaged:

```csharp
<script>
    function toggleDamagesLabel() {
        const checkbox = document.getElementById("RentalDamaged");
        const label = document.getElementById("DamagesIncurredLabel");

        label.textContent = checkbox.checked ? "Damages Incurred" : "Notes";
    }

    document.addEventListener("DOMContentLoaded", toggleDamagesLabel);
</script>
```



This ensures the UI accurately reflects the meaning of the data being entered.
