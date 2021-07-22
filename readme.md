# RustMart Yew Example (Updated for yew 0.18.0 and yew-router 0.15.0)

This fork of shesbabu's excellent demo is updated for the current (July 21)
versions of yew and yew-router. [Origin repository](https://github.com/sheshbabu/rustmart-yew-example)

# Compile Errors

error[E0277]: the trait bound `&std::string::String: IntoPropValue<std::option::Option<Cow<'static, str>>>` is not satisfied
  --> src/components/product_card.rs:39:57
   |
39 |                     <img class="product_card_image" src={&self.props.product.image}/>
   |                                                         ^^^^^^^^^^^^^^^^^^^^^^^^^^^ the trait `IntoPropValue<std::option::Option<Cow<'static, str>>>` is not implemented for `&std::string::String`
   |
  ::: /Users/ken/.cargo/registry/src/github.com-1ecc6299db9ec823/yew-0.18.0/src/virtual_dom/mod.rs:69:47
   |
69 |     pub fn new(key: &'static str, value: impl IntoOptPropValue<AttrValue>) -> Self {
   |                                               --------------------------- required by this bound in `PositionalAttr::new`
   |
   = help: the following implementations were found:
             <std::string::String as IntoPropValue<Cow<'static, str>>>
   = note: required because of the requirements on the impl of `IntoOptPropValue<Cow<'static, str>>` for `&std::string::String`

error[E0277]: the trait bound `types::Product: ImplicitClone` is not satisfied
  --> src/pages/home.rs:97:40
   |
97 |                   <ProductCard product={product} on_add_to_cart=self.props.on_add_to_cart.clone()/>
   |                                        ^^^^^^^^^ the trait `ImplicitClone` is not implemented for `types::Product`
   |
   = note: required because of the requirements on the impl of `IntoPropValue<types::Product>` for `&types::Product`

error[E0277]: the trait bound `&std::string::String: IntoPropValue<std::option::Option<Cow<'static, str>>>` is not satisfied
  --> src/pages/product_detail.rs:90:59
   |
90 |                     <img class="product_detail_image" src={&product.image}/>
   |                                                           ^^^^^^^^^^^^^^^^ the trait `IntoPropValue<std::option::Option<Cow<'static, str>>>` is not implemented for `&std::string::String`
   |
  ::: /Users/ken/.cargo/registry/src/github.com-1ecc6299db9ec823/yew-0.18.0/src/virtual_dom/mod.rs:69:47
   |
69 |     pub fn new(key: &'static str, value: impl IntoOptPropValue<AttrValue>) -> Self {
   |                                               --------------------------- required by this bound in `PositionalAttr::new`
   |
   = help: the following implementations were found:
             <std::string::String as IntoPropValue<Cow<'static, str>>>
   = note: required because of the requirements on the impl of `IntoOptPropValue<Cow<'static, str>>` for `&std::string::String`
