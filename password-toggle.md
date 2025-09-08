### bootrap

<div class="form-group basic animated">
    <div class="input-wrapper">
        <label class="label" for="password"><i class="bi bi-person-fill-lock"></i></label>
        <input type="password" class="form-control" name="password" id="password" placeholder="Enter Password" required>
        
        {{-- Show/Hide password toggle --}}
        <i class="toggle-password bi bi-eye" onclick="togglePassword('password', this)" style="cursor: pointer; position: absolute; right: 40px; top: 50%; transform: translateY(-50%);"></i>
        
        <i class="clear-input"><i class="bi bi-x-circle"></i></i>

        <div>
            @if ($errors->has('password'))
                <small class="text-danger">{{ $errors->first('password') }}</small>
            @endif
        </div>
    </div>
</div>


<div class="form-group basic animated">
    <div class="input-wrapper">
        <label class="label" for="confirm-password"><i class="bi bi-person-fill-lock"></i></label>
        <input type="password" class="form-control" name="password_confirmation" value="{{ old('password_confirmation') }}" id="confirm-password" placeholder="Confirm Password" required>
        
        {{-- Show/Hide confirm password toggle --}}
        <i class="toggle-password bi bi-eye" onclick="togglePassword('confirm-password', this)" style="cursor: pointer; position: absolute; right: 40px; top: 50%; transform: translateY(-50%);"></i>
        
        <i class="clear-input"><i class="bi bi-x-circle"></i></i>

        <div>
            @if ($errors->has('password'))
                <small class="text-danger">{{ $errors->first('password') }}</small>
            @endif
        </div>
    </div>
</div>

### script
<script>
function togglePassword(fieldId, toggleIcon) {
    const input = document.getElementById(fieldId);
    if (input.type === "password") {
        input.type = "text";
        toggleIcon.classList.remove("bi-eye");
        toggleIcon.classList.add("bi-eye-slash");
    } else {
        input.type = "password";
        toggleIcon.classList.remove("bi-eye-slash");
        toggleIcon.classList.add("bi-eye");
    }
}
</script>
