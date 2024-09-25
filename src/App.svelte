<script lang="ts">
  import Activity from "lucide-svelte/icons/activity";
  import ArrowUpRight from "lucide-svelte/icons/arrow-up-right";
  import CircleUser from "lucide-svelte/icons/circle-user";
  import CreditCard from "lucide-svelte/icons/credit-card";
  import DollarSign from "lucide-svelte/icons/dollar-sign";
  import Menu from "lucide-svelte/icons/menu";
  import Cat from "lucide-svelte/icons/cat";
  import Search from "lucide-svelte/icons/search";
  import Users from "lucide-svelte/icons/users";

  import * as Carousel from "$lib/components/ui/carousel/index.js"
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Badge } from "$lib/components/ui/badge/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as Card from "$lib/components/ui/card/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import * as Sheet from "$lib/components/ui/sheet/index.js";
  import * as Table from "$lib/components/ui/table/index.js";
</script>

<div class="flex min-h-screen w-full flex-col">
  <header class="bg-background sticky top-0 border-b flex h-14 md:h-12 items-center gap-2 md:gap-1.5 px-2">
    <nav
      class="hidden flex-col gap-6 text-lg font-medium md:flex md:flex-row md:items-center md:gap-5 md:text-sm lg:gap-6">
      <a href="##" class="flex items-center gap-2 text-lg font-semibold md:text-base">
        <Cat class="h-6 w-6 ml-2" />
        <span class="sr-only">Anime Catalog</span>
      </a>
      <a href="##" class="text-foreground hover:text-foreground transition-colors">
        Home
      </a>
      <a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
        Anime
      </a>
      <a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
        Manga
      </a>
      <a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
        Characters
      </a>
    </nav>
    <Sheet.Root>
      <Sheet.Trigger asChild let:builder>
        <Button
          variant="ghost"
          size="icon"
          class="shrink-0 md:hidden"
          builders={[builder]}
        >
          <Menu />
          <span class="sr-only">Toggle navigation menu</span>
        </Button>
      </Sheet.Trigger>
      <Sheet.Content side="left" class="border-none">
        <nav class="grid gap-6 text-lg font-medium">
          <a href="##" class="flex items-center gap-1.5 text-lg font-semibold">
            <Cat class="h-6 w-6" />
            <span class="sr-only">Anime Catalog</span>
          </a>
          <a href="##" class="hover:text-foreground"> Home </a>
          <a href="##" class="text-muted-foreground hover:text-foreground"> Anime </a>
          <a href="##" class="text-muted-foreground hover:text-foreground"> Manga </a>
          <a href="##" class="text-muted-foreground hover:text-foreground"> Characters </a>
        </nav>
      </Sheet.Content>
    </Sheet.Root>
    <div class="flex w-full items-center gap-4 md:ml-auto md:gap-2 lg:gap-4">
      <form class="ml-auto flex-1 sm:flex-initial">
        <div class="relative">
          <Search class="text-muted-foreground absolute left-2 md:left-2.5 top-2 md:top-1.5 h-5 w-5" />
          <Input
            type="search"
            placeholder="Search animes or mangas..."
            class="pl-9 md:pl-10 sm:w-[300px] md:w-[280px] lg:w-[360px]"
          />
        </div>
      </form>
      <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder>
          <Button
            builders={[builder]}
            variant="secondary"
            size="icon"
            class="rounded-full"
          >
            <CircleUser />
            <span class="sr-only">Toggle user menu</span>
          </Button>
        </DropdownMenu.Trigger>
        <DropdownMenu.Content align="end">
          <DropdownMenu.Label>My Account</DropdownMenu.Label>
          <DropdownMenu.Separator />
          <DropdownMenu.Item>Settings</DropdownMenu.Item>
          <DropdownMenu.Separator />
          <DropdownMenu.Item>Logout</DropdownMenu.Item>
        </DropdownMenu.Content>
      </DropdownMenu.Root>
    </div>
  </header>
  <main class="flex flex-1 flex-col gap-4 p-3.5 md:gap-6 md:p-6">
    <div class="grid gap-4 md:grid-cols-2 md:gap-6 lg:grid-cols-4">
      <Card.Root>
        <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-1">
          <Card.Title class="text-lg font-semibold">Total Revenue</Card.Title>
          <DollarSign class="text-muted-foreground h-5 w-5" />
        </Card.Header>
        <Card.Content>
          <div class="text-2xl font-bold">$45,231.89</div>
          <p class="text-muted-foreground text-xs">+20.1% from last month</p>
        </Card.Content>
      </Card.Root>
      <Card.Root>
        <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-1">
          <Card.Title class="text-lg font-semibold">Subscriptions</Card.Title>
          <Users class="text-muted-foreground h-5 w-5" />
        </Card.Header>
        <Card.Content>
          <div class="text-2xl font-bold">+2350</div>
          <p class="text-muted-foreground text-xs">+180.1% from last month</p>
        </Card.Content>
      </Card.Root>
      <Card.Root>
        <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-1">
          <Card.Title class="text-lg font-sembold">Sales</Card.Title>
          <CreditCard class="text-muted-foreground h-5 w-5" />
        </Card.Header>
        <Card.Content>
          <div class="text-2xl font-bold">+12,234</div>
          <p class="text-muted-foreground text-xs">+19% from last month</p>
        </Card.Content>
      </Card.Root>
      <Card.Root>
        <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-1">
          <Card.Title class="text-lg font-semibold">Active Now</Card.Title>
          <Activity class="text-muted-foreground h-5 w-5" />
        </Card.Header>
        <Card.Content>
          <div class="text-2xl font-bold">+573</div>
          <p class="text-muted-foreground text-xs">+201 since last hour</p>
        </Card.Content>
      </Card.Root>
    </div>
  </main>
</div>
