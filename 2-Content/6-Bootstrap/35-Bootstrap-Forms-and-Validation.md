# Day 35 — Bootstrap Forms & Validation

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 6 — Bootstrap
🧪 **Lab Experiments:** 26, 27

---

## Learning Objectives

By the end of this session, students will be able to:
- Build styled forms using Bootstrap form classes
- Create horizontal, inline, and floating-label forms
- Use Bootstrap's built-in validation styles
- Build a contact/registration form with Bootstrap

---

## 1. Bootstrap Form Controls

```html
<!-- Basic Form -->
<form>
    <div class="mb-3">
        <label for="name" class="form-label">Full Name</label>
        <input type="text" class="form-control" id="name" placeholder="Enter your name">
    </div>
    <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input type="email" class="form-control" id="email" placeholder="name@example.com">
    </div>
    <div class="mb-3">
        <label for="msg" class="form-label">Message</label>
        <textarea class="form-control" id="msg" rows="3"></textarea>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

### Form Control Sizes

```html
<input class="form-control form-control-lg" placeholder="Large">
<input class="form-control" placeholder="Normal">
<input class="form-control form-control-sm" placeholder="Small">
```

---

## 2. Form Layouts

### Horizontal Form

```html
<form>
    <div class="row mb-3">
        <label for="name" class="col-sm-3 col-form-label">Name</label>
        <div class="col-sm-9">
            <input type="text" class="form-control" id="name">
        </div>
    </div>
    <div class="row mb-3">
        <label for="email" class="col-sm-3 col-form-label">Email</label>
        <div class="col-sm-9">
            <input type="email" class="form-control" id="email">
        </div>
    </div>
</form>
```

### Inline Form

```html
<form class="row row-cols-lg-auto g-3 align-items-center">
    <div class="col-12">
        <input type="text" class="form-control" placeholder="Name">
    </div>
    <div class="col-12">
        <input type="email" class="form-control" placeholder="Email">
    </div>
    <div class="col-12">
        <button type="submit" class="btn btn-primary">Subscribe</button>
    </div>
</form>
```

### Floating Labels

```html
<div class="form-floating mb-3">
    <input type="email" class="form-control" id="floatEmail" placeholder="name@example.com">
    <label for="floatEmail">Email address</label>
</div>
<div class="form-floating mb-3">
    <input type="password" class="form-control" id="floatPwd" placeholder="Password">
    <label for="floatPwd">Password</label>
</div>
```

---

## 3. Checkboxes, Radios & Select

```html
<!-- Checkboxes -->
<div class="form-check">
    <input class="form-check-input" type="checkbox" id="html" checked>
    <label class="form-check-label" for="html">HTML</label>
</div>
<div class="form-check">
    <input class="form-check-input" type="checkbox" id="css">
    <label class="form-check-label" for="css">CSS</label>
</div>

<!-- Toggle Switch -->
<div class="form-check form-switch">
    <input class="form-check-input" type="checkbox" id="newsletter">
    <label class="form-check-label" for="newsletter">Subscribe to newsletter</label>
</div>

<!-- Radio Buttons -->
<div class="form-check">
    <input class="form-check-input" type="radio" name="gender" id="male" checked>
    <label class="form-check-label" for="male">Male</label>
</div>
<div class="form-check">
    <input class="form-check-input" type="radio" name="gender" id="female">
    <label class="form-check-label" for="female">Female</label>
</div>

<!-- Select -->
<select class="form-select">
    <option selected disabled>Choose...</option>
    <option value="1">Web Technology</option>
    <option value="2">Data Structures</option>
</select>
```

---

## 4. Bootstrap Validation

```html
<form class="needs-validation" novalidate>
    <div class="mb-3">
        <label for="vName" class="form-label">Name</label>
        <input type="text" class="form-control" id="vName" required>
        <div class="valid-feedback">Looks good!</div>
        <div class="invalid-feedback">Please enter your name.</div>
    </div>
    <div class="mb-3">
        <label for="vEmail" class="form-label">Email</label>
        <input type="email" class="form-control" id="vEmail" required>
        <div class="invalid-feedback">Please enter a valid email.</div>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
</form>

<script>
// Bootstrap validation script
(function () {
    'use strict';
    const forms = document.querySelectorAll('.needs-validation');
    Array.from(forms).forEach(function (form) {
        form.addEventListener('submit', function (event) {
            if (!form.checkValidity()) {
                event.preventDefault();
                event.stopPropagation();
            }
            form.classList.add('was-validated');
        }, false);
    });
})();
</script>
```

---

## Practical Session

### 🧪 Lab Experiments 26 & 27: Bootstrap Registration & Contact Forms

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Forms</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">

    <div class="container my-5">
        <div class="row g-4">
            
            <!-- Registration Form -->
            <div class="col-lg-6">
                <div class="card shadow">
                    <div class="card-header bg-primary text-white">
                        <h4 class="mb-0">Student Registration</h4>
                    </div>
                    <div class="card-body">
                        <form class="needs-validation" novalidate id="regForm">
                            
                            <div class="form-floating mb-3">
                                <input type="text" class="form-control" id="regName" 
                                       placeholder="Full Name" required minlength="2">
                                <label for="regName">Full Name</label>
                                <div class="invalid-feedback">Name required (min 2 chars)</div>
                            </div>

                            <div class="form-floating mb-3">
                                <input type="email" class="form-control" id="regEmail" 
                                       placeholder="Email" required>
                                <label for="regEmail">Email Address</label>
                                <div class="invalid-feedback">Valid email required</div>
                            </div>

                            <div class="form-floating mb-3">
                                <input type="tel" class="form-control" id="regPhone" 
                                       placeholder="Phone" required pattern="\d{10}">
                                <label for="regPhone">Phone Number</label>
                                <div class="invalid-feedback">10-digit number required</div>
                            </div>

                            <div class="form-floating mb-3">
                                <input type="password" class="form-control" id="regPwd" 
                                       placeholder="Password" required minlength="8">
                                <label for="regPwd">Password</label>
                                <div class="invalid-feedback">Min 8 characters</div>
                            </div>

                            <div class="mb-3">
                                <label class="form-label fw-bold">Gender</label>
                                <div>
                                    <div class="form-check form-check-inline">
                                        <input class="form-check-input" type="radio" name="gender" 
                                               id="gMale" value="male" required>
                                        <label class="form-check-label" for="gMale">Male</label>
                                    </div>
                                    <div class="form-check form-check-inline">
                                        <input class="form-check-input" type="radio" name="gender" 
                                               id="gFemale" value="female">
                                        <label class="form-check-label" for="gFemale">Female</label>
                                    </div>
                                    <div class="form-check form-check-inline">
                                        <input class="form-check-input" type="radio" name="gender" 
                                               id="gOther" value="other">
                                        <label class="form-check-label" for="gOther">Other</label>
                                    </div>
                                </div>
                            </div>

                            <div class="mb-3">
                                <label for="regCourse" class="form-label fw-bold">Course</label>
                                <select class="form-select" id="regCourse" required>
                                    <option value="" selected disabled>Select course...</option>
                                    <option>BCA</option>
                                    <option>BBA</option>
                                    <option>B.Tech</option>
                                </select>
                                <div class="invalid-feedback">Please select a course</div>
                            </div>

                            <div class="mb-3">
                                <label class="form-label fw-bold">Interests</label>
                                <div class="form-check">
                                    <input class="form-check-input" type="checkbox" id="iWeb">
                                    <label class="form-check-label" for="iWeb">Web Development</label>
                                </div>
                                <div class="form-check">
                                    <input class="form-check-input" type="checkbox" id="iApp">
                                    <label class="form-check-label" for="iApp">App Development</label>
                                </div>
                                <div class="form-check">
                                    <input class="form-check-input" type="checkbox" id="iAI">
                                    <label class="form-check-label" for="iAI">AI/ML</label>
                                </div>
                            </div>

                            <div class="form-check mb-3">
                                <input class="form-check-input" type="checkbox" id="terms" required>
                                <label class="form-check-label" for="terms">
                                    I agree to the terms and conditions
                                </label>
                                <div class="invalid-feedback">You must agree</div>
                            </div>

                            <button type="submit" class="btn btn-primary w-100 btn-lg">Register</button>
                        </form>
                    </div>
                </div>
            </div>

            <!-- Contact Form -->
            <div class="col-lg-6">
                <div class="card shadow">
                    <div class="card-header bg-success text-white">
                        <h4 class="mb-0">Contact Us</h4>
                    </div>
                    <div class="card-body">
                        <form class="needs-validation" novalidate id="contactForm">
                            
                            <div class="row mb-3">
                                <div class="col-md-6">
                                    <div class="form-floating">
                                        <input type="text" class="form-control" id="cFirst" 
                                               placeholder="First" required>
                                        <label for="cFirst">First Name</label>
                                    </div>
                                </div>
                                <div class="col-md-6 mt-3 mt-md-0">
                                    <div class="form-floating">
                                        <input type="text" class="form-control" id="cLast" 
                                               placeholder="Last" required>
                                        <label for="cLast">Last Name</label>
                                    </div>
                                </div>
                            </div>

                            <div class="form-floating mb-3">
                                <input type="email" class="form-control" id="cEmail" 
                                       placeholder="Email" required>
                                <label for="cEmail">Email</label>
                                <div class="invalid-feedback">Valid email required</div>
                            </div>

                            <div class="mb-3">
                                <label for="cSubject" class="form-label fw-bold">Subject</label>
                                <select class="form-select" id="cSubject" required>
                                    <option value="" selected disabled>Choose subject...</option>
                                    <option>General Inquiry</option>
                                    <option>Admission</option>
                                    <option>Fee Related</option>
                                    <option>Technical Issue</option>
                                </select>
                            </div>

                            <div class="form-floating mb-3">
                                <textarea class="form-control" id="cMessage" 
                                          placeholder="Message" style="height: 120px" required></textarea>
                                <label for="cMessage">Your Message</label>
                                <div class="invalid-feedback">Please enter a message</div>
                            </div>

                            <div class="form-check form-switch mb-3">
                                <input class="form-check-input" type="checkbox" id="cCopy">
                                <label class="form-check-label" for="cCopy">Send me a copy</label>
                            </div>

                            <button type="submit" class="btn btn-success w-100 btn-lg">Send Message</button>
                        </form>
                    </div>
                </div>

                <!-- Alert placeholder -->
                <div class="alert alert-success mt-3 d-none" id="successAlert">
                    ✅ Message sent successfully!
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Bootstrap validation
        (function () {
            'use strict';
            const forms = document.querySelectorAll('.needs-validation');
            Array.from(forms).forEach(function (form) {
                form.addEventListener('submit', function (event) {
                    event.preventDefault();
                    if (!form.checkValidity()) {
                        event.stopPropagation();
                    } else {
                        alert('Form submitted successfully!');
                        form.reset();
                        form.classList.remove('was-validated');
                        return;
                    }
                    form.classList.add('was-validated');
                }, false);
            });
        })();
    </script>

</body>
</html>
```

---

## Summary

| Component | Key Classes |
|-----------|------------|
| Input | `form-control`, `form-control-lg` |
| Label | `form-label`, `col-form-label` |
| Select | `form-select` |
| Checkbox/Radio | `form-check`, `form-check-input` |
| Switch | `form-check form-switch` |
| Floating label | `form-floating` |
| Validation | `needs-validation`, `was-validated`, `valid-feedback`, `invalid-feedback` |

---

*Day 35 of 55 | Unit 6 — Bootstrap | Web Technology (25BCA060)*
