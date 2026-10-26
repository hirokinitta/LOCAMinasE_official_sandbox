<script lang="ts">
 import '../app.css';
 import { page } from '$app/state';import type {LayoutProps} from './$types';let {children}:LayoutProps=$props();const nav=[{label:'TOP',href:'/'},{label:'PORTFOLIO',href:'/portfolio'},{label:'ILLUSTRATION',href:'/illustration'},{label:'ABOUT',href:'/about'}];
</script>
<svelte:head><title>LOCAMinasE — Creative Archive</title><meta name="description" content="LOCAMinasE official creative archive"/></svelte:head><div class="site-shell"><header class="topbar"><a class="brand" href="/">LOCAMinasE<span>OFFICIAL ARCHIVE</span></a><span class="online"><i></i> SYSTEM ONLINE</span></header><nav class="nav" aria-label="メインナビゲーション">{#each nav as item}<a href={item.href} aria-current={page.url.pathname===item.href?'page':undefined}>{item.label}<span>↗</span></a>{/each}</nav><main>{@render children()}</main><footer><span>© LOCAMinasE — DIGITAL CREATIVE ARCHIVE</span><div><a href="/about">CONTACT / SOCIAL LINKS</a><a href="/portfolio">PORTFOLIO</a></div><span>EST. MMXXVI</span></footer></div>


