<script>
	import { enhance } from "$app/forms";
	import Button from "$lib/components/shared/Button.svelte";
	import Input from "$lib/components/shared/Input.svelte";

	/** @type {import("./$types").ActionData} */
	export let form;
</script>

<section class="max-w-xl mx-auto">
	<form action="" method="post" class="border bg-white py-5 px-10" use:enhance>
		<legend class="border-b mb-3 text-gray-700">Login Now</legend>

		<fieldset class="grid gap-4">
			<label for="" class="text-(sm gray-500)">
				<span>Email</span>
				<Input type="email" name="email" class={form?.errors?.email && "border-red"} />
				<small class="text-red">{form?.errors?.email ?? ""}</small>
			</label>

			<label for="" class="text-(sm gray-500)">
				<span>Password</span>
				<Input type="password" name="password" class={form?.errors?.password && "border-red"} />
				<small class="text-red">{form?.errors?.password ?? ""}</small>
			</label>

			<label for="remember" class="flex items-center gap-2 text-(sm gray-500)">
				<input type="checkbox" name="remember" id="remember" class="rounded" />
				<span>Remember Me</span>
			</label>

			<Button class="border-teal border">Login</Button>
		</fieldset>

		<small class="block mt-5 text-gray-600">
			Need an account? <a href="/register" class="text-blue ml-1">register</a>
		</small>
	</form>
</section>
