---
title: Derleyici Uyarısı (düzey 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 46418063625e16385497740a4f7e3d837e923156
ms.sourcegitcommit: a901c4acbfc80ca10663d37c09921f04c5b6dd17
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58142574"
---
# <a name="compiler-warning-level-4-c4800"></a>Derleyici Uyarısı (düzey 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 ve sonraki sürümleri:
> Arasında örtük dönüşüm '*türü*' bool için'. Olası bilgi kaybı
::: moniker-end

Visual Studio 2015'te ve daha önce Düzey 3 uyarısı C4800 şöyledir:
> '*türü*': değer bool 'true' veya 'false' (Performans Uyarısı) zorlama

Bu uyarı bir değeri örtük olarak türe dönüştürüldüğünde oluşturulduğu `bool`. Atayarak bu ileti genellikle, kaynaklanır `int` değişkenlere `bool` değişkenleri burada `int` değişkeni yalnızca verileri içeren **true** ve **false**ve olabilir tür olarak yeniden tanımlanıyor `bool`. İfadeyi türü yeniden yazma, `bool`, ekleyebileceğiniz sonra "`!=0`" ifade, ifade türü sağlayan `bool`. İfade türüne atama `bool` bilinçli olarak böyle tasarlanmıştır uyarı devre dışı değil.

::: moniker range=">= vs-2017"
Bu uyarı, Visual Studio 2017'de gösterilen değil.
::: moniker-end

::: moniker range=">= vs-2019"
Bu uyarı Visual Studio 2019 başlayarak varsayılan olarak kapalıdır. Kullanım __/w__*n*__4800__ C4800 düzey olarak etkinleştirmek için *n* uyarı, veya [/Wall](../../build/reference/compiler-option-warning-level.md) tüm uyarıları etkinleştirmek için Varsayılan olarak kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan tarafından varsayılan olarak kapalıdır](../../preprocessor/compiler-warnings-that-are-off-by-default.md).
::: moniker-end

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4800 oluşturur ve bu sorunun nasıl gösterir:

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