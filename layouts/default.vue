<script setup lang="ts">
const user = useSupabaseUser()
const supaAuth = useSupabaseAuthClient().auth

const logout = async () => {
	await supaAuth.signOut()
	return navigateTo('/')
}
</script>

<template>
	<div>
		<nav class="border-b py-4">
			<Container class="flex items-center justify-between">
				<NuxtLink class="font-bold text-2xl" to="/">
					Nuxt VPS Tutorial
				</NuxtLink>
				<Stack gap="4" items="center">
					<template v-if="user">
						<NuxtLink to="/protected">Protected</NuxtLink>
						<button @click="logout">Logout</button>
					</template>
					<template v-else>
						<NuxtLink to="/login">Login</NuxtLink>
						<NuxtLink
							class="bg-purple-700 font-medium px-4 py-2 rounded-full text-white"
							to="/register"
						>
							Register
						</NuxtLink>
					</template>
				</Stack>
			</Container>
		</nav>
		<Container class="py-12">
			<slot />
		</Container>
	</div>
</template>
