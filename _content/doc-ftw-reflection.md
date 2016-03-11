---
permalink: /docs/reflection/
layout:    docs
title:     Reflection
menu:      Reflection
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Featherweight provides the most comprehensive and coherent known API for
introspection of NI LabVIEW™ datatypes.

All of Featherweight's type-adapting functions rely upon this Reflection API
as the basis upon which idiomatic bindings to the LabVIEW type system are built.

## Type Reflection Categories

Loosely, all types fall into a few categories:

<div class="ui list">
  <div class="item">
    <i class="plus icon"></i>
    <div class="content">
      <div class="header">Primitive Scalar Datatypes</div>
      <div class="list">
        <div class="item">
          <i class="plus icon"></i>
          <div class="content">
            <div class="header">Fixed-Width Types</div>
            <div class="list">
              <div class="item">
                <i class="plus icon"></i>
                <div class="content">
                  <div class="header">Numeric</div>
                  <div class="list">
                    <div class="item"><i class="plus icon"></i>Integers: I8, I16, I32, I64, U8, U16, U32, U64</div>
                    <div class="item"><i class="plus icon"></i>Floating Point: SGL, DBL, EXT</div>
                    <div class="item"><i class="plus icon"></i>Complex: CSGL, CDBL, CEXT</div>
                    <div class="item"><i class="plus icon"></i>Complex: SGLwithUnits, DBLwithUnits, EXTwithUnits</div>
                  </div>
                </div>
              </div>
              <div class="item">
                <i class="plus icon"></i>
                <div class="content">
                  <div class="header">Boolean</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="item">
          <i class="plus icon"></i>
          <div class="content">
            <div class="header">Variable-width Handle Types</div>
            <div class="list">
              <div class="item"><i class="plus icon"></i>String</div>
              <div class="item"><i class="plus icon"></i>Path</div>
              <div class="item"><i class="plus icon"></i>Picture</div>
            </div>
          </div>
        </div>
        <div class="item">
          <i class="folder icon"></i>
          <div class="content">
            <div class="header">themes</div>
            <div class="list">
              <div class="item">
                <i class="folder icon"></i>
                <div class="content">
                  <div class="header">default</div>
                </div>
              </div>
              <div class="item">
                <i class="folder icon"></i>
                <div class="content">
                  <div class="header">my_theme</div>
                  <div class="description">Packaged themes are also available in this folder</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="item">
          <i class="file icon"></i>
          <div class="content">
            <div class="header">theme.config</div>
            <div class="description">Config file for setting packaged themes</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="folder icon"></i>
    <div class="content">
      <div class="header">dist</div>
      <div class="description">Compiled CSS and JS files</div>
      <div class="list">
        <div class="item">
          <i class="folder icon"></i>
          <div class="content">
            <div class="header">components</div>
            <div class="description">Individual component CSS and JS</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="item">
    <i class="file icon"></i>
    <div class="content">
      <div class="header">semantic.json</div>
      <div class="description">Contains build settings for gulp</div>
    </div>
  </div>
</div>

## Omitted Types

For completeness and clarity, below are enumerated a few types that do not
exist:

* Fixed-width strings
* Fixed-width byte arrays (BLOB)
* Enum64

Additionally, some of the following types were strategically omitted:

* toolkit-specific types, such as references to hardware product line toolkits
* semaphore reference types
* entire object models of VI Server (further reflection of the VIServerControl
type is available with existing standard library functionality; Featherweight
does not duplicate this)
* specific reflection of floating point numbers with Units. Use of Units is
generally discouraged and avoided by Featherweight developers.
