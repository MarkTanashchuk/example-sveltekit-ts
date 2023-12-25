<script lang="ts">
  import {
    Breadcrumb,
    BreadcrumbItem,
    Header,
    SideNav,
    SideNavItems,
    SideNavLink,
    Content
  } from 'carbon-components-svelte';
  import Fade from 'carbon-icons-svelte/lib/Fade.svelte';

  const PROJECT_NAME = 'Проєкт';
  const PLATFORM_NAME = 'Інтерактивне навчання';
</script>

<Header company={PROJECT_NAME} platformName={PLATFORM_NAME} isSideNavOpen>
  <Breadcrumb noTrailingSlash>
    <BreadcrumbItem href="/">Dashboard</BreadcrumbItem>
    <BreadcrumbItem href="/reports">Annual reports</BreadcrumbItem>
    <BreadcrumbItem href="/reports/2019" isCurrentPage>2019</BreadcrumbItem>
  </Breadcrumb>
</Header>

<SideNav isOpen>
  <SideNavItems>
    <SideNavLink icon={Fade} text="Посилання 1" href="/" isSelected />
  </SideNavItems>
</SideNav>

<Content>
  <slot />
</Content>
