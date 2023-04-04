Title: WGSL Function Reference
Description: How to use Buffers
TOC: WGSL Function Reference

<div id="func-toc"></div>



<!-- this table is hackly generated here: https://jsgist.org/?src=6d9b87e1be0d1239167f115e59aa54b7 -->
<div class="webgpu-center center data-table">
<div><h2 id="bit-reinterp-builtin-functions">Bit Reinterpretation Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;T&gt;(e : T) -&gt; T </pre></td><td>T is a concrete numeric scalar or concrete numeric vector 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Identity transform.<br> Component-wise when <code>T</code> is a vector.<br> The result is <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;T&gt;(e : S) -&gt; T </pre></td><td>S is i32, u32, or f32 T is not S and is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Reinterpretation of bits as <code>T</code>.<br> The result is the reintepretation of bits in <code>e</code> as a <code>T</code> value. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;vecN&lt;T&gt;&gt;(e : vecN&lt;S&gt;) -&gt; T </pre></td><td>S is i32, u32, or f32 T is not S and is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Component-wise reinterpretation of bits as <code>T</code>.<br> The result is the reintepretation of bits in <code>e</code> as a <code>vecN&lt;T&gt;</code> value. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;T&gt;(e : vec2&lt;f16&gt;) -&gt; T </pre></td><td>T is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Component-wise reinterpretation of bits as <code>T</code>.<br> The result is the reintepretation of the 32 bits in <code>e</code> as a <code>T</code> value, following the internal layout rules. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;vec2&lt;T&gt;&gt;(e : vec4&lt;f16&gt;) -&gt; vec2&lt;T&gt; </pre></td><td>T is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Component-wise reinterpretation of bits as <code>T</code>.<br> The result is the reintepretation of the 64 bits in <code>e</code> as a <code>T</code> value, following the internal layout rules. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;vec2&lt;f16&gt;&gt;(e : T) -&gt; vec2&lt;f16&gt; </pre></td><td>T is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Component-wise reinterpretation of bits as f16.<br> The result is the reintepretation of the 32 bits in <code>e</code> as an f16 value, following the internal layout rules. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn bitcast&lt;vec4&lt;f16&gt;&gt;(e : vec2&lt;T&gt;) -&gt; vec4&lt;f16&gt; </pre></td><td>T is i32, u32, or f32 
     </td><td id="bitcast-builtin"><a href="https://www.w3.org/TR/WGSL/#bitcast-builtin" target="_blank"></a>Component-wise reinterpretation of bits as <code>vec2&lt;f16&gt;</code>.<br> The result is the reintepretation of the 64 bits in <code>e</code> as an f16 value, following the internal layout rules. 
   </td></tr></tbody></table><h2 id="logical-builtin-functions">Logical Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn all(e: vecN&lt;bool&gt;) -&gt; bool </pre></td><td></td><td id="all-builtin"><a href="https://www.w3.org/TR/WGSL/#all-builtin" target="_blank"></a>Returns true if each component of <code>e</code> is true. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn all(e: bool) -&gt; bool </pre></td><td></td><td id="all-builtin"><a href="https://www.w3.org/TR/WGSL/#all-builtin" target="_blank"></a>Returns <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn any(e: vecN&lt;bool&gt;) -&gt; bool </pre></td><td></td><td id="any-builtin"><a href="https://www.w3.org/TR/WGSL/#any-builtin" target="_blank"></a>Returns true if any component of <code>e</code> is true. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn any(e: bool) -&gt; bool </pre></td><td></td><td id="any-builtin"><a href="https://www.w3.org/TR/WGSL/#any-builtin" target="_blank"></a>Returns <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn select(f: T, t: T, cond: bool) -&gt; T </pre></td><td>T is scalar or vector 
     </td><td id="select-builtin"><a href="https://www.w3.org/TR/WGSL/#select-builtin" target="_blank"></a>Returns <code>t</code> when <code>cond</code> is true, and <code>f</code> otherwise. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn select(f: vecN&lt;T&gt;, t: vecN&lt;T&gt;, cond: vecN&lt;bool&gt;) -&gt; vecN&lt;T&gt; </pre></td><td>T is scalar 
     </td><td id="select-builtin"><a href="https://www.w3.org/TR/WGSL/#select-builtin" target="_blank"></a>Component-wise selection. Result component <code>i</code> is evaluated
        as <code>select(f[i], t[i], cond[i])</code>. 
   </td></tr></tbody></table><h2 id="array-builtin-functions">Array Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn arrayLength(p: ptr&lt;storage, array&lt;E&gt;, AM&gt;) -&gt; u32 </pre></td><td>E is an element type for a runtime-sized array, access mode AM is read or read_write 
     </td><td id="arrayLength-builtin"><a href="https://www.w3.org/TR/WGSL/#arrayLength-builtin" target="_blank"></a>
       Returns NRuntime, the number of elements in the runtime-sized array. 
       <p>See § 10.3.4 Buffer Binding Determines Runtime-Sized Array Element Count</p>
   </td></tr></tbody></table><h2 id="numeric-builtin-functions">Numeric Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn abs(e: T ) -&gt; T </pre></td><td>S is AbstractInt, AbstractFloat, i32, u32, f32, or f16T is S, or vecN&lt;S&gt; 
     </td><td id="abs-float-builtin"><a href="https://www.w3.org/TR/WGSL/#abs-float-builtin" target="_blank"></a>
       The absolute value of <code>e</code>. Component-wise when <code>T</code> is a vector. 
       <p>If <code>e</code> is a floating-point type, then the result is <code>e</code> with a positive sign bit.
    If <code>e</code> is an unsigned integer scalar type, then the result is <code>e</code>.
    If <code>e</code> is a signed integer scalar type and evaluates to the largest
    negative value, then the result is <code>e</code>.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn acos(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="acos-builtin"><a href="https://www.w3.org/TR/WGSL/#acos-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful when <code>abs(e)</code> &gt; 1.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn acosh(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="acosh-builtin"><a href="https://www.w3.org/TR/WGSL/#acosh-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful when <code>e</code> &lt; 1.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn asin(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="asin-builtin"><a href="https://www.w3.org/TR/WGSL/#asin-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful when <code>abs(e)</code> &gt; 1.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn asinh(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="asinh-builtin"><a href="https://www.w3.org/TR/WGSL/#asinh-builtin" target="_blank"></a>
       Returns the inverse hyperbolic sine (sinh<sup>-1</sup>) of <code>e</code>, as a hyperbolic angle in radians.<br> That is, approximates <code>x</code> such that <code>sinh</code>(<code>x</code>) = <code>e</code>. 
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn atan(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="atan-builtin"><a href="https://www.w3.org/TR/WGSL/#atan-builtin" target="_blank"></a>
       Returns the principal value, in radians, of the inverse tangent (tan<sup>-1</sup>) of <code>e</code>.<br> That is, approximates <code>x</code> with π/2 ≤ <code>x</code> ≤ π/2, such that <code>tan</code>(<code>x</code>) = <code>e</code>. 
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn atanh(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="atanh-builtin"><a href="https://www.w3.org/TR/WGSL/#atanh-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful when <code>abs(e)</code> ≥ 1.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn atan2(y: T, x: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="atan2-builtin"><a href="https://www.w3.org/TR/WGSL/#atan2-builtin" target="_blank"></a>
       Returns an angle, in radians, in the interval [-π, π] whose tangent is <code>y</code>÷<code>x</code>. 
       <p>The quadrant selected by the result depends on the signs of <code>y</code> and <code>x</code>.
    For example, the function may be implemented as:</p>
       <ul>
        <li data-md="">
         <p><code>atan(y/x)</code> when <code>x</code> &gt; 0</p>
        </li><li data-md="">
         <p><code>atan(y/x)</code> + π when (<code>x</code> &lt; 0) and (<code>y</code> &gt; 0)</p>
        </li><li data-md="">
         <p><code>atan(y/x)</code> - π when (<code>x</code> &lt; 0) and (<code>y</code> &lt; 0)</p>
       </li></ul>
       <p class="note" role="note"><span class="marker">Note:</span> atan2 is ill-defined when <code>y/x</code> is ill-defined, at the origin (<code>x</code>,<code>y</code>) = (0,0), and when <code>y</code> is non-normal or infinite.</p>
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn ceil(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="ceil-builtin"><a href="https://www.w3.org/TR/WGSL/#ceil-builtin" target="_blank"></a>Returns the ceiling of <code>e</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn clamp(e: T, low: T, high: T) -&gt; T </pre></td><td>S is AbstractInt, AbstractFloat, i32, u32, f32, or f16T is S, or vecN&lt;S&gt; 
     </td><td id="clamp"><a href="https://www.w3.org/TR/WGSL/#clamp" target="_blank"></a>
       Restricts the value of <code>e</code> within a range. 
       <p>If <code>T</code> is an integer type, then the result is <code>min(max(e, low), high)</code>.</p>
       <p>If <code>T</code> is a floating-point type, then the result is either <code>min(max(e, low), high)</code>, or the median of the three values <code>e</code>, <code>low</code>, <code>high</code>.</p>
       <p>Component-wise when <code>T</code> is a vector.</p>
       <p>If <code>low</code> is greater than <code>high</code>, then:</p>
       <ul>
        <li data-md="">
         <p>It is a shader-creation error if <code>low</code> and <code>high</code> are const-expressions.</p>
        </li><li data-md="">
         <p>It is a pipeline-creation error if <code>low</code> and <code>high</code> are override-expressions.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn cos(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="cos-builtin"><a href="https://www.w3.org/TR/WGSL/#cos-builtin" target="_blank"></a>Returns the cosine of <code>e</code>, where <code>e</code> is in radians. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn cosh(arg: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="cosh-builtin"><a href="https://www.w3.org/TR/WGSL/#cosh-builtin" target="_blank"></a>
       Returns the hyperbolic cosine of <code>arg</code>, where <code>arg</code> is a hyperbolic angle in radians.
    Approximates the pure mathematical function (<em>e</em><sup>arg</sup> + <em>e</em><sup>−arg</sup>)÷2,
    but not necessarily computed that way. 
       <p>Component-wise when <code>T</code> is a vector</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn countLeadingZeros(e: T) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="countLeadingZeros-builtin"><a href="https://www.w3.org/TR/WGSL/#countLeadingZeros-builtin" target="_blank"></a>The number of consecutive 0 bits starting from the most significant bit
        of <code>e</code>, when <code>T</code> is a scalar type.<br> Component-wise when <code>T</code> is a vector.<br> Also known as "clz" in some languages. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn countOneBits(e: T) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="countOneBits-builtin"><a href="https://www.w3.org/TR/WGSL/#countOneBits-builtin" target="_blank"></a>The number of 1 bits in the representation of <code>e</code>.<br> Also known as "population count".<br> Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn countTrailingZeros(e: T) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="countTrailingZeros-builtin"><a href="https://www.w3.org/TR/WGSL/#countTrailingZeros-builtin" target="_blank"></a>The number of consecutive 0 bits starting from the least significant bit
        of <code>e</code>, when <code>T</code> is a scalar type.<br> Component-wise when <code>T</code> is a vector.<br> Also known as "ctz" in some languages. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn cross(e1: vec3&lt;T&gt;, e2: vec3&lt;T&gt;) -&gt; vec3&lt;T&gt; </pre></td><td>T is AbstractFloat, f32, or f16 
     </td><td id="cross-builtin"><a href="https://www.w3.org/TR/WGSL/#cross-builtin" target="_blank"></a>Returns the cross product of <code>e1</code> and <code>e2</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn degrees(e1: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="degrees-builtin"><a href="https://www.w3.org/TR/WGSL/#degrees-builtin" target="_blank"></a>Converts radians to degrees, approximating <code>e1</code>&nbsp;×&nbsp;180&nbsp;÷&nbsp;π. Component-wise when <code>T</code> is a vector 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn determinant(e: matCxC&lt;T&gt;) -&gt; T </pre></td><td>T is AbstractFloat, f32, or f16 
     </td><td id="determinant-builtin"><a href="https://www.w3.org/TR/WGSL/#determinant-builtin" target="_blank"></a>Returns the determinant of <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn distance(e1: T, e2: T) -&gt; S </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="distance-builtin"><a href="https://www.w3.org/TR/WGSL/#distance-builtin" target="_blank"></a>Returns the distance between <code>e1</code> and <code>e2</code> (e.g. <code>length(e1 - e2)</code>). 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dot(e1: vecN&lt;T&gt;, e2: vecN&lt;T&gt;) -&gt; T </pre></td><td>T is AbstractInt, AbstractFloat, i32, u32, f32, or f16 
     </td><td id="dot-builtin"><a href="https://www.w3.org/TR/WGSL/#dot-builtin" target="_blank"></a>Returns the dot product of <code>e1</code> and <code>e2</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn exp(e1: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="exp-builtin"><a href="https://www.w3.org/TR/WGSL/#exp-builtin" target="_blank"></a>Returns the natural exponentiation of <code>e1</code> (e.g. <code>e</code><sup><code>e1</code></sup>). Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn exp2(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="exp2-builtin"><a href="https://www.w3.org/TR/WGSL/#exp2-builtin" target="_blank"></a>Returns 2 raised to the power <code>e</code> (e.g. <code>2</code><sup><code>e</code></sup>). Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn extractBits(e: T, offset: u32, count: u32) -&gt; T </pre></td><td>T is i32 or vecN&lt;i32&gt; 
     </td><td id="extractBits-signed-builtin"><a href="https://www.w3.org/TR/WGSL/#extractBits-signed-builtin" target="_blank"></a>
       Reads bits from an integer, with sign extension. 
       <p>When <code>T</code> is a scalar type, then:</p>
       <ul>
        <li><code>w</code> is the bit width of <code>T</code> 
        </li><li><code>o = min(offset, w)</code> 
        </li><li><code>c = min(count, w - o)</code> 
        </li><li>The result is 0 if <code>c</code> is 0. 
        </li><li>Otherwise, bits <code>0..c - 1</code> of the result are copied from bits <code>o..o + c - 1</code> of <code>e</code>.
       Other bits of the result are the same as bit <code>c - 1</code> of the result. 
       </li></ul>
        Component-wise when <code>T</code> is a vector. 
       <p>If <code>count</code> + <code>offset</code> is greater than <code>w</code>, then:</p>
       <ul>
        <li data-md="">
         <p>It is a shader-creation error if <code>count</code> and <code>offset</code> are const-expressions.</p>
        </li><li data-md="">
         <p>It is a pipeline-creation error if <code>count</code> and <code>offset</code> are override-expressions.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn extractBits(e: T, offset: u32, count: u32) -&gt; T </pre></td><td>T is u32 or vecN&lt;u32&gt; 
     </td><td id="extractBits-unsigned-builtin"><a href="https://www.w3.org/TR/WGSL/#extractBits-unsigned-builtin" target="_blank"></a>
       Reads bits from an integer, without sign extension. 
       <p>When <code>T</code> is a scalar type, then:</p>
       <ul>
        <li><code>w</code> is the bit width of <code>T</code> 
        </li><li><code>o = min(offset, w)</code> 
        </li><li><code>c = min(count, w - o)</code> 
        </li><li>The result is 0 if <code>c</code> is 0. 
        </li><li>Otherwise, bits <code>0..c - 1</code> of the result are copied from bits <code>o..o + c - 1</code> of <code>e</code>.
       Other bits of the result are 0. 
       </li></ul>
        Component-wise when <code>T</code> is a vector. 
       <p>If <code>count</code> + <code>offset</code> is greater than <code>w</code>, then:</p>
       <ul>
        <li data-md="">
         <p>It is a shader-creation error if <code>count</code> and <code>offset</code> are const-expressions.</p>
        </li><li data-md="">
         <p>It is a pipeline-creation error if <code>count</code> and <code>offset</code> are override-expressions.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn faceForward(e1: T, e2: T, e3: T) -&gt; T </pre></td><td>T is vecN&lt;AbstractFloat&gt;, vecN&lt;f32&gt;, or vecN&lt;f16&gt; 
     </td><td id="faceForward-builtin"><a href="https://www.w3.org/TR/WGSL/#faceForward-builtin" target="_blank"></a>Returns <code>e1</code> if <code>dot(e2, e3)</code> is negative, and <code>-e1</code> otherwise. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn firstLeadingBit(e: T) -&gt; T </pre></td><td>T is i32 or vecN&lt;i32&gt; 
     </td><td id="firstLeadingBit-signed-builtin"><a href="https://www.w3.org/TR/WGSL/#firstLeadingBit-signed-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> Since signed integers use twos-complement representation,
the sign bit appears in the most significant bit position.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn firstLeadingBit(e: T) -&gt; T </pre></td><td>T is u32 or vecN&lt;u32&gt; 
     </td><td id="firstLeadingBit-unsigned-builtin"><a href="https://www.w3.org/TR/WGSL/#firstLeadingBit-unsigned-builtin" target="_blank"></a>
       For scalar <code>T</code>, the result is: 
       <ul>
        <li><code>T(-1)</code> if <code>e</code> is zero. 
        </li><li>Otherwise the position of the most significant 1
            bit in <code>e</code>. 
       </li></ul>
        Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn firstTrailingBit(e: T) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="firstTrailingBit-builtin"><a href="https://www.w3.org/TR/WGSL/#firstTrailingBit-builtin" target="_blank"></a>
       For scalar <code>T</code>, the result is: 
       <ul>
        <li><code>T(-1)</code> if <code>e</code> is zero. 
        </li><li>Otherwise the position of the least significant 1
            bit in <code>e</code>. 
       </li></ul>
        Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn floor(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="floor-builtin"><a href="https://www.w3.org/TR/WGSL/#floor-builtin" target="_blank"></a>Returns the floor of <code>e</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn fma(e1: T, e2: T, e3: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="fma-builtin"><a href="https://www.w3.org/TR/WGSL/#fma-builtin" target="_blank"></a>
       Returns <code>e1 * e2 + e3</code>. Component-wise when <code>T</code> is a vector. 
       <p class="note" role="note"><span class="marker">Note:</span> The name <code>fma</code> is short for "fused multiply add".</p>
       <p class="note" role="note"><span class="marker">Note:</span> The IEEE-754 <code>fusedMultiplyAdd</code> operation computes the intermediate results
    as if with unbounded range and precision, and only the final result is rounded
    to the destination type.
    However, the § 14.6.1 Floating Point Accuracy rule for <code>fma</code> allows an implementation
    which performs an ordinary multiply to the target type followed by an ordinary addition.
    In this case the intermediate values may overflow or lose accuracy, and the overall
    operation is not "fused" at all.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn fract(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="fract-builtin"><a href="https://www.w3.org/TR/WGSL/#fract-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> Valid results are in the closed interval [0, 1.0].
For example, if <code>e</code> is a very small negative number, then <code>fract(e)</code> may be 1.0.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_f32 </pre></td><td>T is f32 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_f32</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_f16 </pre></td><td>T is f16 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_f16</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_abstract </pre></td><td>T is AbstractFloat 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_abstract</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_vecN_f32 </pre></td><td>T is vecN&lt;f32&gt; 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_vecN_f32</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_vecN_f16 </pre></td><td>T is vecN&lt;f16&gt; 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_vecN_f16</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn frexp(e: T) -&gt; __frexp_result_vecN_abstract </pre></td><td>T is vecN&lt;AbstractFloat&gt; 
     </td><td id="frexp-builtin"><a href="https://www.w3.org/TR/WGSL/#frexp-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__frexp_result_vecN_abstract</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn insertBits(e: T, newbits: T, offset: u32, count: u32) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="insertBits-builtin"><a href="https://www.w3.org/TR/WGSL/#insertBits-builtin" target="_blank"></a>
       Sets bits in an integer. 
       <p>When <code>T</code> is a scalar type, then:</p>
       <ul>
        <li><code>w</code> is the bit width of <code>T</code> 
        </li><li><code>o = min(offset, w)</code> 
        </li><li><code>c = min(count, w - o)</code> 
        </li><li>The result is <code>e</code> if <code>c</code> is 0. 
        </li><li>Otherwise,
       bits <code>o..o + c - 1</code> of the result are copied from bits <code>0..c - 1</code> of <code>newbits</code>.
       Other bits of the result are copied from <code>e</code>. 
       </li></ul>
        Component-wise when <code>T</code> is a vector. 
       <p>If <code>count</code> + <code>offset</code> is greater than <code>w</code>, then:</p>
       <ul>
        <li data-md="">
         <p>It is a shader-creation error if <code>count</code> and <code>offset</code> are const-expressions.</p>
        </li><li data-md="">
         <p>It is a pipeline-creation error if <code>count</code> and <code>offset</code> are override-expressions.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn inverseSqrt(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="inverseSqrt-builtin"><a href="https://www.w3.org/TR/WGSL/#inverseSqrt-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful if <code>e</code> ≤ 0.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn ldexp(e1: T, e2: I) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; I is AbstractInt, i32, vecN&lt;AbstractInt&gt;, or vecN&lt;i32&gt; I is a vector if and only if T is a vector I is concrete if and only if T is a concrete 
     </td><td id="ldexp-builtin"><a href="https://www.w3.org/TR/WGSL/#ldexp-builtin" target="_blank"></a>
       Returns <code>e1 * 2</code><sup><code>e2</code></sup>, except: 
       <ul>
        <li data-md="">
         <p>The result may be zero if <code>e2</code> + <em>bias</em> ≤ 0.</p>
        </li><li data-md="">
         <p>If <code>e2</code> &gt; <em>bias</em> + 1</p>
         <ul>
          <li data-md="">
           <p>It is a shader-creation error if <code>e2</code> is a const-expression.</p>
          </li><li data-md="">
           <p>It is a pipeline-creation error if <code>e2</code> is an override-expression.</p>
          </li><li data-md="">
           <p>Otherwise the result is an indeterminate value for <code>T</code>.</p>
         </li></ul>
       </li></ul>
       <p>Here, <em>bias</em> is the exponent bias of the floating point format:</p>
       <ul>
        <li data-md="">
         <p>15 for <code>f16</code></p>
        </li><li data-md="">
         <p>127 for <code>f32</code></p>
        </li><li data-md="">
         <p>1023 for AbstractFloat, when AbstractFloat is IEEE-754 binary64</p>
       </li></ul>
       <p>If <code>x</code> is zero or a finite normal value for its type, then:</p>
       <blockquote> x = ldexp(frexp(x).fract, frexp(x).exp) </blockquote>
       <p>Component-wise when <code>T</code> is a vector.</p>
       <p class="note" role="note"><span class="marker">Note:</span> A mnemonic for the name <code>ldexp</code> is "load exponent".
    The name may have been taken from the corresponding instruction in the floating point unit of
    the PDP-11.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn length(e: T) -&gt; S </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="length-builtin"><a href="https://www.w3.org/TR/WGSL/#length-builtin" target="_blank"></a>
       Returns the length of <code>e</code>.<br> Evaluates to the absolute value of <code>e</code> if <code>T</code> is scalar.<br> Evaluates to <code>sqrt(e[0]</code><sup><code>2</code></sup> <code>+ e[1]</code><sup><code>2</code></sup> <code>+ ...)</code> if <code>T</code> is a vector type. 
       <p class="note" role="note"><span class="marker">Note:</span> The scalar case may be evaluated as <code>sqrt(e * e)</code>,
        which may unnecessarily overflow or lose accuracy.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn log(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="log-builtin"><a href="https://www.w3.org/TR/WGSL/#log-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful if <code>e</code> &lt; 0.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn log2(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="log2-builtin"><a href="https://www.w3.org/TR/WGSL/#log2-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The result is not mathematically meaningful if <code>e</code> &lt; 0.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn max(e1: T, e2: T) -&gt; T </pre></td><td>S is AbstractInt, AbstractFloat, i32, u32, f32, or f16T is S, or vecN&lt;S&gt; 
     </td><td id="max-float-builtin"><a href="https://www.w3.org/TR/WGSL/#max-float-builtin" target="_blank"></a>
       Returns <code>e2</code> if <code>e1</code> is less than <code>e2</code>, and <code>e1</code> otherwise. Component-wise when <code>T</code> is a vector. 
       <p>If <code>e1</code> and <code>e2</code> are floating-point values, then:</p>
       <ul>
        <li data-md="">
         <p>If both <code>e1</code> and <code>e2</code> are denormalized, then the result may be <em>either</em> value.</p>
        </li><li data-md="">
         <p>If one operand is a NaN, the other is returned.</p>
        </li><li data-md="">
         <p>If both operands are NaNs, a NaN is returned.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn min(e1: T, e2: T) -&gt; T </pre></td><td>S is AbstractInt, AbstractFloat, i32, u32, f32, or f16T is S, or vecN&lt;S&gt; 
     </td><td id="min-float-builtin"><a href="https://www.w3.org/TR/WGSL/#min-float-builtin" target="_blank"></a>
       Returns <code>e2</code> if <code>e2</code> is less than <code>e1</code>, and <code>e1</code> otherwise. Component-wise when <code>T</code> is a vector. 
       <p>If <code>e1</code> and <code>e2</code> are floating-point values, then:</p>
       <ul>
        <li data-md="">
         <p>If both <code>e1</code> and <code>e2</code> are denormalized, then the result may be <em>either</em> value.</p>
        </li><li data-md="">
         <p>If one operand is a NaN, the other is returned.</p>
        </li><li data-md="">
         <p>If both operands are NaNs, a NaN is returned.</p>
       </li></ul>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn mix(e1: T, e2: T, e3: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="mix-builtin"><a href="https://www.w3.org/TR/WGSL/#mix-builtin" target="_blank"></a>Returns the linear blend of <code>e1</code> and <code>e2</code> (e.g. <code>e1 * (1 - e3) + e2 * e3</code>). Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn mix(e1: T2, e2: T2, e3: T) -&gt; T2 </pre></td><td>T is AbstractFloat, f32, or f16 T2 is vecN&lt;T&gt; 
     </td><td id="mix-builtin"><a href="https://www.w3.org/TR/WGSL/#mix-builtin" target="_blank"></a>Returns the component-wise linear blend of <code>e1</code> and <code>e2</code>,
        using scalar blending factor <code>e3</code> for each component.<br> Same as <code>mix(e1, e2, T2(e3))</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_f32 </pre></td><td>T is f32 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_f32</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_f16 </pre></td><td>T is f16 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_f16</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_abstract </pre></td><td>T is AbstractFloat 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_abstract</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_vecN_f32 </pre></td><td>T is vecN&lt;f32&gt; 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_vecN_f32</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_vecN_f16 </pre></td><td>T is vecN&lt;f16&gt; 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_vecN_f16</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn modf(e: T) -&gt; __modf_result_vecN_abstract </pre></td><td>T is vecN&lt;AbstractFloat&gt; 
     </td><td id="modf-builtin"><a href="https://www.w3.org/TR/WGSL/#modf-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> A value cannot be explicitly declared with the type <code>__modf_result_vecN_abstract</code>,
but a value may infer the type.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn normalize(e: vecN&lt;T&gt; ) -&gt; vecN&lt;T&gt; </pre></td><td>T is AbstractFloat, f32, or f16 
     </td><td id="normalize-builtin"><a href="https://www.w3.org/TR/WGSL/#normalize-builtin" target="_blank"></a>Returns a unit vector in the same direction as <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn pow(e1: T, e2: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="pow-builtin"><a href="https://www.w3.org/TR/WGSL/#pow-builtin" target="_blank"></a>Returns <code>e1</code> raised to the power <code>e2</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn quantizeToF16(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="quantizeToF16-builtin"><a href="https://www.w3.org/TR/WGSL/#quantizeToF16-builtin" target="_blank"></a>
       <p class="note" role="note"><span class="marker">Note:</span> The vec2&lt;f32&gt; case is the same as <code>unpack2x16float(pack2x16float(e))</code>.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn radians(e1: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="radians-builtin"><a href="https://www.w3.org/TR/WGSL/#radians-builtin" target="_blank"></a>Converts degrees to radians, approximating <code>e1</code>&nbsp;×&nbsp;π&nbsp;÷&nbsp;180. Component-wise when <code>T</code> is a vector 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn reflect(e1: T, e2: T) -&gt; T </pre></td><td>T is vecN&lt;AbstractFloat&gt;, vecN&lt;f32&gt;, or vecN&lt;f16&gt; 
     </td><td id="reflect-builtin"><a href="https://www.w3.org/TR/WGSL/#reflect-builtin" target="_blank"></a>For the incident vector <code>e1</code> and surface orientation <code>e2</code>, returns the reflection direction <code>e1 - 2 * dot(e2, e1) * e2</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn refract(e1: T, e2: T, e3: I) -&gt; T </pre></td><td>T is vecN&lt;I&gt; I is AbstractFloat, f32, or f16 
     </td><td id="refract-builtin"><a href="https://www.w3.org/TR/WGSL/#refract-builtin" target="_blank"></a>For the incident vector <code>e1</code> and surface normal <code>e2</code>, and the ratio of
    indices of refraction <code>e3</code>,
    let <code>k = 1.0 - e3 * e3 * (1.0 - dot(e2, e1) * dot(e2, e1))</code>.
    If <code>k &lt; 0.0</code>, returns the refraction vector 0.0, otherwise return the refraction vector <code>e3 * e1 - (e3 * dot(e2, e1) + sqrt(k)) * e2</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn reverseBits(e: T) -&gt; T </pre></td><td>T is i32, u32, vecN&lt;i32&gt;, or vecN&lt;u32&gt; 
     </td><td id="reverseBits-builtin"><a href="https://www.w3.org/TR/WGSL/#reverseBits-builtin" target="_blank"></a>Reverses the bits in <code>e</code>:  The bit at position <code>k</code> of the result equals the
        bit at position <code>31 -k</code> of <code>e</code>.<br> Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn round(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="round-builtin"><a href="https://www.w3.org/TR/WGSL/#round-builtin" target="_blank"></a>Result is the integer <code>k</code> nearest to <code>e</code>, as a floating point value.<br> When <code>e</code> lies halfway between integers <code>k</code> and <code>k + 1</code>,
        the result is <code>k</code> when <code>k</code> is even, and <code>k + 1</code> when <code>k</code> is odd.<br> Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn saturate(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="saturate-float-builtin"><a href="https://www.w3.org/TR/WGSL/#saturate-float-builtin" target="_blank"></a>Returns <code>clamp(e, 0.0, 1.0)</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn sign(e: T) -&gt; T </pre></td><td>S is AbstractInt, AbstractFloat, i32, f32, or f16T is S, or vecN&lt;S&gt; 
     </td><td id="sign-builtin"><a href="https://www.w3.org/TR/WGSL/#sign-builtin" target="_blank"></a>
       Result is: 
       <ul>
        <li> 1 when <code>e</code> &gt; 0 
        </li><li> 0 when <code>e</code> = 0 
        </li><li> -1 when <code>e</code> &lt; 0 
       </li></ul>
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn sin(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="sin-builtin"><a href="https://www.w3.org/TR/WGSL/#sin-builtin" target="_blank"></a>Returns the sine of <code>e</code>, where <code>e</code> is in radians. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn sinh(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="sinh-builtin"><a href="https://www.w3.org/TR/WGSL/#sinh-builtin" target="_blank"></a>
       Returns the hyperbolic sine of <code>e</code>, where <code>e</code> is a hyperbolic angle in radians.
    Approximates the pure mathematical function
    (<em>e</em><sup>arg</sup> − <em>e</em><sup>−arg</sup>)÷2,
    but not necessarily computed that way. 
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn smoothstep(low: T, high: T, x: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="smoothstep-builtin"><a href="https://www.w3.org/TR/WGSL/#smoothstep-builtin" target="_blank"></a>
       Returns the smooth Hermite interpolation between 0 and 1. Component-wise when <code>T</code> is a vector. 
       <p>For scalar <code>T</code>, the result is <code>t * t * (3.0 - 2.0 * t)</code>,
    where <code>t = clamp((x - low) / (high - low), 0.0, 1.0)</code>.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn sqrt(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="sqrt-builtin"><a href="https://www.w3.org/TR/WGSL/#sqrt-builtin" target="_blank"></a>Returns the square root of <code>e</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn step(edge: T, x: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="step-builtin"><a href="https://www.w3.org/TR/WGSL/#step-builtin" target="_blank"></a>Returns 1.0 if <code>edge</code> ≤ <code>x</code>, and 0.0 otherwise. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn tan(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="tan-builtin"><a href="https://www.w3.org/TR/WGSL/#tan-builtin" target="_blank"></a>Returns the tangent of <code>e</code>, where <code>e</code> is in radians. Component-wise when <code>T</code> is a vector. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn tanh(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="tanh-builtin"><a href="https://www.w3.org/TR/WGSL/#tanh-builtin" target="_blank"></a>
       Returns the hyperbolic tangent of <code>e</code>, where <code>e</code> is a hyperbolic angle in radians.
    Approximates the pure mathematical function
    (<em>e</em><sup>arg</sup> − <em>e</em><sup>−arg</sup>) ÷ (<em>e</em><sup>arg</sup> + <em>e</em><sup>−arg</sup>)
    but not necessarily computed that way. 
       <p>Component-wise when <code>T</code> is a vector.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn transpose(e: matRxC&lt;T&gt;) -&gt; matCxR&lt;T&gt; </pre></td><td>T is AbstractFloat, f32, or f16 
     </td><td id="transpose-builtin"><a href="https://www.w3.org/TR/WGSL/#transpose-builtin" target="_blank"></a>Returns the transpose of <code>e</code>. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn trunc(e: T) -&gt; T </pre></td><td>S is AbstractFloat, f32, or f16T is S or vecN&lt;S&gt; 
     </td><td id="trunc-builtin"><a href="https://www.w3.org/TR/WGSL/#trunc-builtin" target="_blank"></a>Returns truncate(<code>e</code>), the nearest whole number whose absolute value
    is less than or equal to the absolute value of <code>e</code>. Component-wise when <code>T</code> is a vector. 
   </td></tr></tbody></table><h2 id="derivative-builtin-functions">Derivative Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdx(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdx-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdx-builtin" target="_blank"></a>
       Partial derivative of <code>e</code> with respect to window x coordinates.
    The result is the same as either <code>dpdxFine(e)</code> or <code>dpdxCoarse(e)</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdxCoarse(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdxCoarse-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdxCoarse-builtin" target="_blank"></a>
       Returns the partial derivative of <code>e</code> with respect to window x coordinates using local differences.
    This may result in fewer unique positions that <code>dpdxFine(e)</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdxFine(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdxFine-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdxFine-builtin" target="_blank"></a>
       Returns the partial derivative of <code>e</code> with respect to window x coordinates. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdy(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdy-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdy-builtin" target="_blank"></a>
       Partial derivative of <code>e</code> with respect to window y coordinates.
    The result is the same as either <code>dpdyFine(e)</code> or <code>dpdyCoarse(e)</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdyCoarse(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdyCoarse-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdyCoarse-builtin" target="_blank"></a>
       Returns the partial derivative of <code>e</code> with respect to window y coordinates using local differences.
    This may result in fewer unique positions that <code>dpdyFine(e)</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn dpdyFine(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="dpdyFine-builtin"><a href="https://www.w3.org/TR/WGSL/#dpdyFine-builtin" target="_blank"></a>
       Returns the partial derivative of <code>e</code> with respect to window y coordinates. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn fwidth(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="fwidth-builtin"><a href="https://www.w3.org/TR/WGSL/#fwidth-builtin" target="_blank"></a>
       Returns <code>abs(dpdx(e)) + abs(dpdy(e))</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn fwidthCoarse(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="fwidthCoarse-builtin"><a href="https://www.w3.org/TR/WGSL/#fwidthCoarse-builtin" target="_blank"></a>
       Returns <code>abs(dpdxCoarse(e)) + abs(dpdyCoarse(e))</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn fwidthFine(e: T) -&gt; T </pre></td><td>T is f32 or vecN&lt;f32&gt; 
     </td><td id="fwidthFine-builtin"><a href="https://www.w3.org/TR/WGSL/#fwidthFine-builtin" target="_blank"></a>
       Returns <code>abs(dpdxFine(e)) + abs(dpdyFine(e))</code>. 
       <p>Returns an indeterminate value if called in non-uniform control flow.</p>
   </td></tr></tbody></table><h2 id="texture-builtin-functions">Texture Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T) -&gt; u32 </pre></td><td>ST is i32, u32, or f32 F is a texel format A is an access mode T is texture_1d&lt;ST&gt; or texture_storage_1d&lt;F,A&gt; 
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T, level: L) -&gt; u32 </pre></td><td>
       ST is i32, u32, or f32 T is texture_1d&lt;ST&gt; 
       L is i32, or u32
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T) -&gt; vec2&lt;u32&gt; </pre></td><td>ST is i32, u32, or f32 F is a texel format A is an access mode T is texture_2d&lt;ST&gt;, texture_2d_array&lt;ST&gt;, texture_cube&lt;ST&gt;, texture_cube_array&lt;ST&gt;, texture_multisampled_2d&lt;ST&gt;, texture_depth_2d, texture_depth_2d_array, texture_depth_cube, texture_depth_cube_array, texture_depth_multisampled_2d, texture_storage_2d&lt;F,A&gt;, texture_storage_2d_array&lt;F,A&gt;,
               or texture_external 
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T, level: L) -&gt; vec2&lt;u32&gt; </pre></td><td>
       ST is i32, u32, or f32 T is texture_2d&lt;ST&gt;, texture_2d_array&lt;ST&gt;, texture_cube&lt;ST&gt;, texture_cube_array&lt;ST&gt;, texture_depth_2d, texture_depth_2d_array, texture_depth_cube, or texture_depth_cube_array 
       L is i32, or u32
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T) -&gt; vec3&lt;u32&gt; </pre></td><td>ST is i32, u32, or f32 F is a texel format A is an access mode T is texture_3d&lt;ST&gt; or texture_storage_3d&lt;F,A&gt; 
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureDimensions(t: T, level: L) -&gt; vec3&lt;u32&gt; </pre></td><td>
       ST is i32, u32, or f32 T is texture_3d&lt;ST&gt; 
       L is i32, or u32
      </td><td id="texturedimensions"><a href="https://www.w3.org/TR/WGSL/#texturedimensions" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The coordinate dimensions of the texture.</p>
<p>That is, the result provides the integer bounds on the coordinates of the logical texel address,
excluding the mip level count, array size, and sample count.</p>
<p>For textures based on cubes, the results are the dimensions of each face of the cube.
Cube faces are square, so the x and y components of the result are equal.</p>
<p>If <code>level</code> is outside the range <code>[0, textureNumLevels(t))</code> then an indeterminate value for the return type may be returned.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_2d&lt;ST&gt;, s: sampler, coords: vec2&lt;f32&gt;) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_2d&lt;ST&gt;, s: sampler, coords: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_2d_array&lt;ST&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 A is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_2d_array&lt;ST&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 A is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_cube&lt;ST&gt;, s: sampler, coords: vec3&lt;f32&gt;) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(component: C, t: texture_cube_array&lt;ST&gt;, s: sampler, coords: vec3&lt;f32&gt;, array_index: A) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 A is i32, or u32 ST is i32, u32, or f32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_cube, s: sampler, coords: vec3&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGather(t: texture_depth_cube_array, s: sampler, coords: vec3&lt;f32&gt;, array_index: A) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegather"><a href="https://www.w3.org/TR/WGSL/#texturegather" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>A four component vector with components extracted from the specified channel from the selected texels, as described above.</p>
<div class="example wgsl global-scope no-marker" id="example-16e82a5f">
    
    <div class="marker">EXAMPLE: Gather components from texels in 2D texture</div>
<pre class="highlight"><c- o="">@</c-><c- n="">group</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- o="">@</c-><c- n="">binding</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- n="">var</c-> <c- n="">t</c->: <c- nc="">texture_2d</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">;</c->
<c- o="">@</c-><c- n="">group</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- o="">@</c-><c- n="">binding</c-><c- p="">(</c-><c- mi="">1</c-><c- p="">)</c-> <c- n="">var</c-> <c- n="">dt</c->: <c- nc="">texture_depth_2d</c-><c- p="">;</c->
<c- o="">@</c-><c- n="">group</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- o="">@</c-><c- n="">binding</c-><c- p="">(</c-><c- mi="">2</c-><c- p="">)</c-> <c- n="">var</c-> <c- n="">s</c->: <c- nc="">sampler</c-><c- p="">;</c->

<c- k="">fn</c-> <c- nf="">gather_x_components</c-><c- p="">(</c-><c- n="">c</c->: <c- nc="">vec2</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">)</c-> -&gt; <c- nc="">vec4</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-> <c- p="">{</c->
  <c- k="">return</c-> <c- n="">textureGather</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">,</c-><c- n="">t</c-><c- p="">,</c-><c- n="">s</c-><c- p="">,</c-><c- n="">c</c-><c- p="">);</c->
<c- p="">}</c->
<c- k="">fn</c-> <c- nf="">gather_y_components</c-><c- p="">(</c-><c- n="">c</c->: <c- nc="">vec2</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">)</c-> -&gt; <c- nc="">vec4</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-> <c- p="">{</c->
  <c- k="">return</c-> <c- n="">textureGather</c-><c- p="">(</c-><c- mi="">1</c-><c- p="">,</c-><c- n="">t</c-><c- p="">,</c-><c- n="">s</c-><c- p="">,</c-><c- n="">c</c-><c- p="">);</c->
<c- p="">}</c->
<c- k="">fn</c-> <c- nf="">gather_z_components</c-><c- p="">(</c-><c- n="">c</c->: <c- nc="">vec2</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">)</c-> -&gt; <c- nc="">vec4</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-> <c- p="">{</c->
  <c- k="">return</c-> <c- n="">textureGather</c-><c- p="">(</c-><c- mi="">2</c-><c- p="">,</c-><c- n="">t</c-><c- p="">,</c-><c- n="">s</c-><c- p="">,</c-><c- n="">c</c-><c- p="">);</c->
<c- p="">}</c->
<c- k="">fn</c-> <c- nf="">gather_depth_components</c-><c- p="">(</c-><c- n="">c</c->: <c- nc="">vec2</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">)</c-> -&gt; <c- nc="">vec4</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-> <c- p="">{</c->
  <c- k="">return</c-> <c- n="">textureGather</c-><c- p="">(</c-><c- n="">dt</c-><c- p="">,</c-><c- n="">s</c-><c- p="">,</c-><c- n="">c</c-><c- p="">);</c->
<c- p="">}</c->
</pre>
   </div></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_cube, s: sampler_comparison, coords: vec3&lt;f32&gt;, depth_ref: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureGatherCompare(t: texture_depth_cube_array, s: sampler_comparison, coords: vec3&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturegathercompare"><a href="https://www.w3.org/TR/WGSL/#texturegathercompare" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>A four component vector with comparison result for the selected texels, as described above.</p>
<div class="example wgsl global-scope no-marker" id="example-e6a4066b">
    
    <div class="marker">EXAMPLE: Gather depth comparison</div>
<pre class="highlight"><c- o="">@</c-><c- n="">group</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- o="">@</c-><c- n="">binding</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- n="">var</c-> <c- n="">dt</c->: <c- nc="">texture_depth_2d</c-><c- p="">;</c->
<c- o="">@</c-><c- n="">group</c-><c- p="">(</c-><c- mi="">0</c-><c- p="">)</c-> <c- o="">@</c-><c- n="">binding</c-><c- p="">(</c-><c- mi="">1</c-><c- p="">)</c-> <c- n="">var</c-> <c- n="">s</c->: <c- nc="">sampler</c-><c- p="">;</c->

<c- k="">fn</c-> <c- nf="">gather_depth_compare</c-><c- p="">(</c-><c- n="">c</c->: <c- nc="">vec2</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-><c- p="">,</c-> <c- n="">depth_ref</c->: <c- b="">f32</c-><c- p="">)</c-> -&gt; <c- nc="">vec4</c-><c- o="">&lt;</c-><c- b="">f32</c-><c- o="">&gt;</c-> <c- p="">{</c->
  <c- k="">return</c-> <c- n="">textureGatherCompare</c-><c- p="">(</c-><c- n="">dt</c-><c- p="">,</c-><c- n="">s</c-><c- p="">,</c-><c- n="">c</c-><c- p="">,</c-><c- n="">depth_ref</c-><c- p="">);</c->
<c- p="">}</c->
</pre>
   </div></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_1d&lt;ST&gt;, coords: C, level: L) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 L is i32, or u32 ST is i32, u32, or f32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_2d&lt;ST&gt;, coords: vec2&lt;C&gt;, level: L) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 L is i32, or u32 ST is i32, u32, or f32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_2d_array&lt;ST&gt;, coords: vec2&lt;C&gt;, array_index: A, level: L) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 A is i32, or u32 L is i32, or u32 ST is i32, u32, or f32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_3d&lt;ST&gt;, coords: vec3&lt;C&gt;, level: L) -&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 L is i32, or u32 ST is i32, u32, or f32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_multisampled_2d&lt;ST&gt;, coords: vec2&lt;C&gt;, sample_index: S)-&gt; vec4&lt;ST&gt; </pre></td><td>C is i32, or u32 S is i32, or u32 ST is i32, u32, or f32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_depth_2d, coords: vec2&lt;C&gt;, level: L) -&gt; f32 </pre></td><td>C is i32, or u32 L is i32, or u32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_depth_2d_array, coords: vec2&lt;C&gt;, array_index: A, level: L) -&gt; f32 </pre></td><td>C is i32, or u32 A is i32, or u32 L is i32, or u32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_depth_multisampled_2d, coords: vec2&lt;C&gt;, sample_index: S)-&gt; f32 </pre></td><td>C is i32, or u32 S is i32, or u32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureLoad(t: texture_external, coords: vec2&lt;C&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>C is i32, or u32 
      </td><td id="textureload"><a href="https://www.w3.org/TR/WGSL/#textureload" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The unfiltered texel data.</p>
<p>The logical texel address is invalid if:</p>
<ul>
    <li data-md="">
     <p>any element of <code>coords</code> is outside the range <code>[0, textureDimensions(t, level))</code> for the corresponding element, or</p>
    </li><li data-md="">
     <p><code>array_index</code> is outside the range <code>[0, textureNumLayers(t))</code>, or</p>
    </li><li data-md="">
     <p><code>level</code> is outside the range <code>[0, textureNumLevels(t))</code>, or</p>
    </li><li data-md="">
     <p><code>sample_index</code> is outside the range <code>[0, textureNumSamples(s))</code></p>
   </li></ul>
<p>If the logical texel addresss is invalid, the built-in function returns one of:</p>
<ul>
    <li data-md="">
     <p>The data for some texel within bounds of the texture</p>
    </li><li data-md="">
     <p>A vector (0,0,0,0) or (0,0,0,1) of the appropriate type for non-depth textures</p>
    </li><li data-md="">
     <p>0.0 for depth textures</p>
   </li></ul></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureNumLayers(t: T) -&gt; u32 </pre></td><td>F is a texel format A is an access mode ST is i32, u32, or f32 T is texture_2d_array&lt;ST&gt;, texture_cube_array&lt;ST&gt;, texture_depth_2d_array, texture_depth_cube_array,
                               or texture_storage_2d_array&lt;F,A&gt; 
      </td><td id="texturenumlayers"><a href="https://www.w3.org/TR/WGSL/#texturenumlayers" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>If the texture is based on cubes, returns the number of cubes in the cube arrayed texture.</p>
<p>Otherwise returns the number of layers (homogeneous grids of texels) in the arrayed texture.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureNumLevels(t: T) -&gt; u32 </pre></td><td>ST is i32, u32, or f32 T is texture_1d&lt;ST&gt;, texture_2d&lt;ST&gt;, texture_2d_array&lt;ST&gt;, texture_3d&lt;ST&gt;, texture_cube&lt;ST&gt;, texture_cube_array&lt;ST&gt;, texture_depth_2d, texture_depth_2d_array, texture_depth_cube, or texture_depth_cube_array 
      </td><td id="texturenumlevels"><a href="https://www.w3.org/TR/WGSL/#texturenumlevels" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The mip level count for the texture.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureNumSamples(t: T) -&gt; u32 </pre></td><td>ST is i32, u32, or f32 T is texture_multisampled_2d&lt;ST&gt; or texture_depth_multisampled_2d 
      </td><td id="texturenumsamples"><a href="https://www.w3.org/TR/WGSL/#texturenumsamples" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sample count for the multisampled texture.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_1d&lt;f32&gt;, s: sampler, coords: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: T, s: sampler, coords: vec3&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>T is texture_3d&lt;f32&gt;, or texture_cube&lt;f32&gt; 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_3d&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, offset: vec3&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_cube_array&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, array_index: A) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;) -&gt; f32 </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_cube, s: sampler, coords: vec3&lt;f32&gt;) -&gt; f32 </pre></td><td>
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSample(t: texture_depth_cube_array, s: sampler, coords: vec3&lt;f32&gt;, array_index: A) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesample"><a href="https://www.w3.org/TR/WGSL/#texturesample" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sampled value.</p>
<p>An indeterminate value results if called in non-uniform control flow.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, bias: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, bias: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, bias: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, bias: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: T, s: sampler, coords: vec3&lt;f32&gt;, bias: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>T is texture_3d&lt;f32&gt;, or texture_cube&lt;f32&gt; 
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_3d&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, bias: f32, offset: vec3&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBias(t: texture_cube_array&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, array_index: A, bias: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplebias"><a href="https://www.w3.org/TR/WGSL/#texturesamplebias" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sampled value.</p>
<p>An indeterminate value results if called in non-uniform control flow.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_cube, s: sampler_comparison, coords: vec3&lt;f32&gt;, depth_ref: f32) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompare(t: texture_depth_cube_array, s: sampler_comparison, coords: vec3&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecompare"><a href="https://www.w3.org/TR/WGSL/#texturesamplecompare" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>A value in the range <code>[0.0..1.0]</code>.</p>
<p>Each sampled texel is compared against the reference value using the comparison
operator defined by the <code>sampler_comparison</code>, resulting in either a <code>0</code> or <code>1</code> value for each texel.</p>
<p>If the sampler uses bilinear filtering then the returned value is
the filtered average of these values, otherwise the comparison result of a
single texel is returned.</p>
<p>An indeterminate value results if called in non-uniform control flow.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_2d, s: sampler_comparison, coords: vec2&lt;f32&gt;, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_2d_array, s: sampler_comparison, coords: vec2&lt;f32&gt;, array_index: A, depth_ref: f32, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_cube, s: sampler_comparison, coords: vec3&lt;f32&gt;, depth_ref: f32) -&gt; f32 </pre></td><td>
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleCompareLevel(t: texture_depth_cube_array, s: sampler_comparison, coords: vec3&lt;f32&gt;, array_index: A, depth_ref: f32) -&gt; f32 </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplecomparelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplecomparelevel" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>A value in the range <code>[0.0..1.0]</code>.</p>
<p>The <code>textureSampleCompareLevel</code> function is the same as <code>textureSampleCompare</code>, except that:</p>
<ul>
    <li data-md="">
     <p><code>textureSampleCompareLevel</code> always samples texels from mip level 0.</p>
     <ul>
      <li data-md="">
       <p>The function does not compute derivatives.</p>
      </li><li data-md="">
       <p>There is no requirement for <code>textureSampleCompareLevel</code> to be invoked in uniform control flow.</p>
     </li></ul>
    </li><li data-md="">
     <p><code>textureSampleCompareLevel</code> may be invoked in any shader stage.</p>
   </li></ul></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, ddx: vec2&lt;f32&gt;, ddy: vec2&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, ddx: vec2&lt;f32&gt;, ddy: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, ddx: vec2&lt;f32&gt;, ddy: vec2&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, ddx: vec2&lt;f32&gt;, ddy: vec2&lt;f32&gt;, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: T, s: sampler, coords: vec3&lt;f32&gt;, ddx: vec3&lt;f32&gt;, ddy: vec3&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>T is texture_3d&lt;f32&gt;, or texture_cube&lt;f32&gt; 
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_3d&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, ddx: vec3&lt;f32&gt;, ddy: vec3&lt;f32&gt;, offset: vec3&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleGrad(t: texture_cube_array&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, array_index: A, ddx: vec3&lt;f32&gt;, ddy: vec3&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplegrad"><a href="https://www.w3.org/TR/WGSL/#texturesamplegrad" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sampled value.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, level: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_2d&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, level: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, level: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_2d_array&lt;f32&gt;, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, level: f32, offset: vec2&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: T, s: sampler, coords: vec3&lt;f32&gt;, level: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>T is texture_3d&lt;f32&gt;, or texture_cube&lt;f32&gt; 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_3d&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, level: f32, offset: vec3&lt;i32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_cube_array&lt;f32&gt;, s: sampler, coords: vec3&lt;f32&gt;, array_index: A, level: f32) -&gt; vec4&lt;f32&gt; </pre></td><td>A is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;, level: L) -&gt; f32 </pre></td><td>L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_2d, s: sampler, coords: vec2&lt;f32&gt;, level: L, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, level: L) -&gt; f32 </pre></td><td>A is i32, or u32 L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_2d_array, s: sampler, coords: vec2&lt;f32&gt;, array_index: A, level: L, offset: vec2&lt;i32&gt;) -&gt; f32 </pre></td><td>A is i32, or u32 L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_cube, s: sampler, coords: vec3&lt;f32&gt;, level: L) -&gt; f32 </pre></td><td>L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleLevel(t: texture_depth_cube_array, s: sampler, coords: vec3&lt;f32&gt;, array_index: A, level: L) -&gt; f32 </pre></td><td>A is i32, or u32 L is i32, or u32 
      </td><td id="texturesamplelevel"><a href="https://www.w3.org/TR/WGSL/#texturesamplelevel" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sampled value.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureSampleBaseClampToEdge(t: T, s: sampler, coords: vec2&lt;f32&gt;) -&gt; vec4&lt;f32&gt; </pre></td><td>T is texture_2d&lt;f32&gt; or texture_external 
      </td><td id="textureSampleBaseClampToEdge"><a href="https://www.w3.org/TR/WGSL/#textureSampleBaseClampToEdge" target="_blank"></a></td></tr><tr><td colspan="3"><p><strong>Returns:</strong></p>
<p>The sampled value.</p></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureStore(t: texture_storage_1d&lt;F,write&gt;, coords: C, value: vec4&lt;CF&gt;) </pre></td><td>F is a texel format C is i32, or u32 CF depends on the storage texel format F. See the texel format table for the mapping of texel
        format to channel format. 
      </td><td id="texturestore"><a href="https://www.w3.org/TR/WGSL/#texturestore" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureStore(t: texture_storage_2d&lt;F,write&gt;, coords: vec2&lt;C&gt;, value: vec4&lt;CF&gt;) </pre></td><td>F is a texel format C is i32, or u32 CF depends on the storage texel format F. See the texel format table for the mapping of texel
        format to channel format. 
      </td><td id="texturestore"><a href="https://www.w3.org/TR/WGSL/#texturestore" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureStore(t: texture_storage_2d_array&lt;F,write&gt;, coords: vec2&lt;C&gt;, array_index: A, value: vec4&lt;CF&gt;) </pre></td><td>F is a texel format C is i32, or u32 A is i32, or u32 CF depends on the storage texel format F. See the texel format table for the mapping of texel
        format to channel format. 
      </td><td id="texturestore"><a href="https://www.w3.org/TR/WGSL/#texturestore" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn textureStore(t: texture_storage_3d&lt;F,write&gt;, coords: vec3&lt;C&gt;, value: vec4&lt;CF&gt;) </pre></td><td>F is a texel format C is i32, or u32 CF depends on the storage texel format F. See the texel format table for the mapping of texel
        format to channel format. 
      </td><td id="texturestore"><a href="https://www.w3.org/TR/WGSL/#texturestore" target="_blank"></a></td></tr></tbody></table><h2 id="atomic-builtin-functions">Atomic Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl">fn atomicLoad(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;) -&gt; T </pre></td><td></td><td id="atomic-load"><a href="https://www.w3.org/TR/WGSL/#atomic-load" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl">fn atomicStore(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) </pre></td><td></td><td id="atomic-store"><a href="https://www.w3.org/TR/WGSL/#atomic-store" target="_blank"></a></td></tr><tr><td><pre class="tableprettyprint lang-wgsl">fn atomicAdd(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicSub(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicMax(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicMin(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicAnd(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicOr(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T fn atomicXor(atomic_ptr: ptr&lt;AS, atomic&lt;T&gt;, read_write&gt;, v: T) -&gt; T </pre></td><td></td><td id="atomic-rmw"><a href="https://www.w3.org/TR/WGSL/#atomic-rmw" target="_blank"></a></td></tr></tbody></table><h2 id="pack-builtin-functions">Data Packing Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn pack4x8snorm(e: vec4&lt;f32&gt;) -&gt; u32 </pre></td><td></td><td id="pack4x8snorm-builtin"><a href="https://www.w3.org/TR/WGSL/#pack4x8snorm-builtin" target="_blank"></a>Converts four normalized floating point values to 8-bit signed integers, and then combines them
        into one <code>u32</code> value.<br> Component <code>e[i]</code> of the input is converted to an 8-bit twos complement integer value
        ⌊ 0.5 + 127 × min(1, max(-1, e[i])) ⌋ which is then placed in bits
        8 × <code>i</code> through
        8 × <code>i</code> + 7 of the result. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn pack4x8unorm(e: vec4&lt;f32&gt;) -&gt; u32 </pre></td><td></td><td id="pack4x8unorm-builtin"><a href="https://www.w3.org/TR/WGSL/#pack4x8unorm-builtin" target="_blank"></a>Converts four normalized floating point values to 8-bit unsigned integers, and then combines them
        into one <code>u32</code> value.<br> Component <code>e[i]</code> of the input is converted to an 8-bit unsigned integer value
        ⌊ 0.5 + 255 × min(1, max(0, e[i])) ⌋ which is then placed in bits
        8 × <code>i</code> through
        8 × <code>i</code> + 7 of the result. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn pack2x16snorm(e: vec2&lt;f32&gt;) -&gt; u32 </pre></td><td></td><td id="pack2x16snorm-builtin"><a href="https://www.w3.org/TR/WGSL/#pack2x16snorm-builtin" target="_blank"></a>Converts two normalized floating point values to 16-bit signed integers, and then combines them
        into one <code>u32</code> value.<br> Component <code>e[i]</code> of the input is converted to a 16-bit twos complement integer value
        ⌊ 0.5 + 32767 × min(1, max(-1, e[i])) ⌋ which is then placed in bits
        16 × <code>i</code> through
        16 × <code>i</code> + 15 of the result. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn pack2x16unorm(e: vec2&lt;f32&gt;) -&gt; u32 </pre></td><td></td><td id="pack2x16unorm-builtin"><a href="https://www.w3.org/TR/WGSL/#pack2x16unorm-builtin" target="_blank"></a>Converts two normalized floating point values to 16-bit unsigned integers, and then combines them
        into one <code>u32</code> value.<br> Component <code>e[i]</code> of the input is converted to a 16-bit unsigned integer value
        ⌊ 0.5 + 65535 × min(1, max(0, e[i])) ⌋ which is then placed in bits
        16 × <code>i</code> through
        16 × <code>i</code> + 15 of the result. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn pack2x16float(e: vec2&lt;f32&gt;) -&gt; u32 </pre></td><td></td><td id="pack2x16float-builtin"><a href="https://www.w3.org/TR/WGSL/#pack2x16float-builtin" target="_blank"></a>
       Converts two floating point values to half-precision floating point numbers, and then combines
        them into one <code>u32</code> value.<br> Component <code>e[i]</code> of the input is converted to a IEEE-754 binary16 value, which is then
        placed in bits
        16 × <code>i</code> through
        16 × <code>i</code> + 15 of the result.
        See § 14.6.2 Floating Point Conversion. 
       <p>If either <code>e[0]</code> or <code>e[1]</code> is outside the finite range of binary16 then:</p>
       <ul>
        <li data-md="">
         <p>It is a shader-creation error if <code>e</code> is a const-expression.</p>
        </li><li data-md="">
         <p>It is a pipeline-creation error if <code>e</code> is an override-expression.</p>
        </li><li data-md="">
         <p>Otherwise the result is an indeterminate value for u32.</p>
       </li></ul>
   </td></tr></tbody></table><h2 id="unpack-builtin-functions">Data Unpacking Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn unpack4x8snorm(e: u32) -&gt; vec4&lt;f32&gt; </pre></td><td></td><td id="unpack4x8snorm-builtin"><a href="https://www.w3.org/TR/WGSL/#unpack4x8snorm-builtin" target="_blank"></a>Decomposes a 32-bit value into four 8-bit chunks, then reinterprets
        each chunk as a signed normalized floating point value.<br> Component <code>i</code> of the result is max(v ÷ 127, -1), where <code>v</code> is the interpretation of
        bits 8×<code>i</code> through 8×<code>i + 7</code> of <code>e</code> as a twos-complement signed integer. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn unpack4x8unorm(e: u32) -&gt; vec4&lt;f32&gt; </pre></td><td></td><td id="unpack4x8unorm-builtin"><a href="https://www.w3.org/TR/WGSL/#unpack4x8unorm-builtin" target="_blank"></a>Decomposes a 32-bit value into four 8-bit chunks, then reinterprets
        each chunk as an unsigned normalized floating point value.<br> Component <code>i</code> of the result is <code>v</code> ÷ 255, where <code>v</code> is the interpretation of
        bits 8×<code>i</code> through 8×<code>i + 7</code> of <code>e</code> as an unsigned integer. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn unpack2x16snorm(e: u32) -&gt; vec2&lt;f32&gt; </pre></td><td></td><td id="unpack2x16snorm-builtin"><a href="https://www.w3.org/TR/WGSL/#unpack2x16snorm-builtin" target="_blank"></a>Decomposes a 32-bit value into two 16-bit chunks, then reinterprets
        each chunk as a signed normalized floating point value.<br> Component <code>i</code> of the result is max(v ÷ 32767, -1), where <code>v</code> is the interpretation of
        bits 16×<code>i</code> through 16×<code>i + 15</code> of <code>e</code> as a twos-complement signed integer. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn unpack2x16unorm(e: u32) -&gt; vec2&lt;f32&gt; </pre></td><td></td><td id="unpack2x16unorm-builtin"><a href="https://www.w3.org/TR/WGSL/#unpack2x16unorm-builtin" target="_blank"></a>Decomposes a 32-bit value into two 16-bit chunks, then reinterprets
        each chunk as an unsigned normalized floating point value.<br> Component <code>i</code> of the result is <code>v</code> ÷ 65535, where <code>v</code> is the interpretation of
        bits 16×<code>i</code> through 16×<code>i + 15</code> of <code>e</code> as an unsigned integer. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn unpack2x16float(e: u32) -&gt; vec2&lt;f32&gt; </pre></td><td></td><td id="unpack2x16float-builtin"><a href="https://www.w3.org/TR/WGSL/#unpack2x16float-builtin" target="_blank"></a>Decomposes a 32-bit value into two 16-bit chunks, and reinterpets each chunk
        as a floating point value.<br> Component <code>i</code> of the result is the f32 representation of <code>v</code>,
        where <code>v</code> is the interpretation of bits 16×<code>i</code> through 16×<code>i + 15</code> of <code>e</code> as an IEEE-754 binary16 value.
        See § 14.6.2 Floating Point Conversion. 
   </td></tr></tbody></table><h2 id="sync-builtin-functions">Synchronization Built-in Functions</h2><table><thead><th>Function</th><th>Parameter Types</th><th>Description</th></thead><tbody><tr><td><pre class="tableprettyprint lang-wgsl"> fn storageBarrier() </pre></td><td></td><td id="storageBarrier-builtin"><a href="https://www.w3.org/TR/WGSL/#storageBarrier-builtin" target="_blank"></a>Executes a control barrier synchronization function that affects
    memory and atomic operations in the storage address
    space. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn workgroupBarrier() </pre></td><td></td><td id="workgroupBarrier-builtin"><a href="https://www.w3.org/TR/WGSL/#workgroupBarrier-builtin" target="_blank"></a>Executes a control barrier synchronization function that affects
    memory and atomic operations in the workgroup address
    space. 
   </td></tr><tr><td><pre class="tableprettyprint lang-wgsl"> fn workgroupUniformLoad(p : ptr&lt;workgroup, T&gt;) -&gt; T </pre></td><td>T is a concrete plain type with a fixed footprint that does not contain any atomic types 
     </td><td id="workgroupUniformLoad-builtin"><a href="https://www.w3.org/TR/WGSL/#workgroupUniformLoad-builtin" target="_blank"></a>
       Returns the value pointed to by <code>p</code> to all invocations in the workgroup.
    The return value is uniform. <code>p</code> must be a uniform value. 
       <p>Executes a control barrier synchronization function that affects
    memory and atomic operations in the workgroup address
    space.</p>
   </td></tr></tbody></table></div>
</div>

<p class="copyright" data-fill-with="copyright"><a href="https://www.w3.org/Consortium/Legal/ipr-notice#Copyright">Copyright</a> © 2023 <a href="https://www.w3.org/">World Wide Web Consortium</a>. <abbr title="World Wide Web Consortium">W3C</abbr><sup>®</sup> <a href="https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer">liability</a>, <a href="https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks">trademark</a> and <a href="https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document" rel="license">permissive document license</a> rules apply. </p>

<!-- keep this at the bottom of the article -->
<link href="webgpu-wgsl-function-reference.css" rel="stylesheet">
<script type="module" src="webgpu-wgsl-function-reference.js"></script>