<script lang="ts">
	import { Slider as SliderPrimitive } from 'bits-ui'
	import { cn } from '$lib/utils'

	type $$Props = SliderPrimitive.Props

	let className: $$Props['class'] = undefined
	export let value: $$Props['value'] = [0]
	export { className as class }
</script>

<div class="flex gap-5">
	<SliderPrimitive.Root
		bind:value
		class={cn('relative flex w-full touch-none select-none items-center gap-5', className)}
		{...$$restProps}
	>
		<span class="relative h-[2px] w-full grow overflow-hidden rounded-full bg-black">
			<SliderPrimitive.Range class="absolute h-full" />
		</span>
		<SliderPrimitive.Thumb
			class="block h-4 w-4 rounded-full bg-black transition-colors focus-visible:outline-none disabled:pointer-events-none disabled:opacity-50"
		/>
	</SliderPrimitive.Root>

	<button class="w-10">
		{value}%
	</button>
</div>
