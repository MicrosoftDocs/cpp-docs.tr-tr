---
title: Derleyici Uyarısı (düzey 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 828b38aeb184741af284f2d7722017b24f6255a3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198594"
---
# <a name="compiler-warning-level-4-c4800"></a>Derleyici Uyarısı (düzey 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 ve üzeri:
> '*Type*' türünden bool 'a örtük dönüştürme. Olası bilgi kaybı
::: moniker-end

C4800, Visual Studio 2015 ve önceki sürümlerde 3. düzey bir uyarıdır:
> '*Type*': değer bool ' true ' veya ' false ' olarak zorlanıyor (performans uyarısı)

Bu uyarı bir değer `bool`türüne örtük olarak dönüştürüldüğünde oluşturulur. Genellikle, bu ileti, `int` değişkeninin yalnızca **true** ve **false**değerlerini içerdiği ve `bool`türü olarak yeniden bildirilebileceği `bool` değişkenlerine `int` değişkenleri atanırken oluşur. `bool`türünü kullanmak için ifadeyi yeniden yazamıyoruz, ifadeye "`!=0`" ekleyebilirsiniz ve bu ifade türü `bool`sağlar. İfadeyi `bool` türüne atama, tasarım ile olan uyarıyı devre dışı bırakmaz.

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
