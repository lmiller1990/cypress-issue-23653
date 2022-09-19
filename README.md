Reproducing https://github.com/cypress-io/cypress/issues/23653

1. `yarn`
2. `yarn vue-tsc --noEmit`


Error!

```
$ yarn vue-tsc --noEmit                                                    main
yarn run v1.22.11
$ /home/lachlan/code/dump/vue3-vite/node_modules/.bin/vue-tsc --noEmit
src/components/HelloWorld.cy.ts:6:14 - error TS2769: No overload matches this call.
  The last overload gave the following error.
    Argument of type 'ComponentPublicInstanceConstructor<{ $: ComponentInternalInstance; $data: {}; $props: Partial<{}> & Omit<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>> & VNodeProps & AllowedComponentProps & ComponentCustomProps, never>; ... 10 more ...; $watch(source: string | Function, cb: Function, ...' is not assignable to parameter of type 'ComponentOptionsWithObjectProps<__VLS_TypePropsToRuntimeProps<{ label: string; }>, {}, unknown, {}, {}, ComponentOptionsMixin, ComponentOptionsMixin, string[], string, Readonly<...> & { ...; }, {}>'.
      Type 'ComponentPublicInstanceConstructor<{ $: ComponentInternalInstance; $data: {}; $props: Partial<{}> & Omit<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>> & VNodeProps & AllowedComponentProps & ComponentCustomProps, never>; ... 10 more ...; $watch(source: string | Function, cb: Function, ...' is not assignable to type 'ComponentOptionsBase<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>> & { [x: `on${Capitalize<string>}`]: ((...args: any[]) => any) | undefined; }, ... 8 more ..., {}>'.
        Types of property 'setup' are incompatible.
          Type '((this: void, props: Readonly<LooseRequired<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>>>>, ctx: SetupContext<...>) => void | ... 2 more ... | Promise<...>) | undefined' is not assignable to type '((this: void, props: Readonly<LooseRequired<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>> & { [x: `on${Capitalize<string>}`]: ((...args: any[]) => any) | undefined; }>>, ctx: SetupContext<...>) => void | ... 2 more ... | Promise<...>) | undefined'.
            Type '(this: void, props: Readonly<LooseRequired<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>>>>, ctx: SetupContext<...>) => void | ... 2 more ... | Promise<...>' is not assignable to type '(this: void, props: Readonly<LooseRequired<Readonly<ExtractPropTypes<__VLS_TypePropsToRuntimeProps<{ label: string; }>>> & { [x: `on${Capitalize<string>}`]: ((...args: any[]) => any) | undefined; }>>, ctx: SetupContext<...>) => void | ... 2 more ... | Promise<...>'.
              Types of parameters 'ctx' and 'ctx' are incompatible.
                Type 'SetupContext<string[]>' is not assignable to type 'SetupContext<{}>'.
                  Type '{}' is missing the following properties from type 'string[]': length, pop, push, concat, and 29 more.

6     cy.mount(HelloWorld, {})
               ~~~~~~~~~~

  node_modules/cypress/vue/dist/index.d.ts:82:25
    82 export declare function mount<PropsOptions extends Readonly<ComponentPropsOptions>, RawBindings, D, C extends ComputedOptions = {}, M extends Record<string, Function> = {}, E extends EmitsOptions = Record<string, any>, Mixin extends ComponentOptionsMixin = ComponentOptionsMixin, Extends extends ComponentOptionsMixin = ComponentOptionsMixin, EE extends string = string>(componentOptions: ComponentOptionsWithObjectProps<PropsOptions, RawBindings, D, C, M, E, Mixin, Extends, EE>, options?: CyMountOptions<ExtractPropTypes<PropsOptions> & PublicProps, D>): Cypress.Chainable;
                               ~~~~~
    The last overload is declared here.


Found 1 error in src/components/HelloWorld.cy.ts:6
```
