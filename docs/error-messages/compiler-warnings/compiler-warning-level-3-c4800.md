---
title: Derleyici Uyarısı (düzey 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: a516be2e6e1966c3249ed21cc6d480ddea8b5ec1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220021"
---
# <a name="compiler-warning-level-4-c4800"></a>Derleyici Uyarısı (düzey 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 ve üzeri:
> '*Type*' türünden bool 'a örtük dönüştürme. Olası bilgi kaybı
::: moniker-end

C4800, Visual Studio 2015 ve önceki sürümlerde 3. düzey bir uyarıdır:
> '*Type*': değer bool ' true ' veya ' false ' olarak zorlanıyor (performans uyarısı)

Bu uyarı, bir değer örtük olarak türüne dönüştürüldüğünde oluşturulur **`bool`** . Genellikle, bu ileti **`int`** **`bool`** **`int`** değişkenin yalnızca değerler **`true`** ve ve **`false`** tür olarak yeniden bildirilebileceği değişkenlere **`bool`** atanması nedeniyle oluşur. Türü kullanmak için ifadeyi yeniden yazamıyoruz, ifadeye **`bool`** " `!=0` " ekleyebilirsiniz **`bool`** . İfadeyi türüne atama **`bool`** , tasarım ile olan uyarıyı devre dışı bırakmaz.

::: moniker range=">= vs-2017"
Bu uyarı, Visual Studio 2017 ' de yayılmaz.
::: moniker-end

::: moniker range=">= vs-2019"
Bu uyarı, Visual Studio 2019 ' den başlayarak varsayılan olarak kapalıdır. Varsayılan olarak kapalı olan tüm uyarıları etkinleştirmek için bir düzey *n* uyarısı veya [/duvar](../../build/reference/compiler-option-warning-level.md) olarak C4800 etkinleştirmek üzere __/w__*n*__4800__ kullanın. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).
::: moniker-end

## <a name="example"></a>Örnek

Aşağıdaki örnek C4800 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4800.cpp
// compile with: /W4 /w44800
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```
