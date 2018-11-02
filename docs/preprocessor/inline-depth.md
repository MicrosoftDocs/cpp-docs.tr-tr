---
title: inline_depth
ms.date: 11/04/2016
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: b08578406fab4fe3a025d502f71cfd90f8dca75b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471372"
---
# <a name="inlinedepth"></a>inline_depth
Bir derinlikteyse (çağrı grafında içinde) daha büyük ise, hiçbir işlevin satır içine alınmış şekilde satır içi buluşsal arama derinliğini belirtir *n*.

## <a name="syntax"></a>Sözdizimi

```
#pragma inline_depth( [n] )
```

## <a name="remarks"></a>Açıklamalar

Bu pragma denetimleri olarak işaretlenmiş İşlevler, satır içi [satır içi](../cpp/inline-functions-cpp.md) ve [__inline](../cpp/inline-functions-cpp.md) veya altında otomatik olarak satır içine alınmış `/Ob2` seçeneği.

*n* 0 ve burada 255 çağrı grafında sınırsız bir derinlik anlamına gelir ve sıfır satır içi genişletmeyi engeller 255 arasında bir değer olabilir.  Zaman *n* belirtilmezse, varsayılan (254) kullanılır.

**İnline_depth** pragma kaç kez bir dizi işlev çağrısının genişletilebileceğini denetler. Örneğin, satır içi derinliği dört ise ve A B'yi çağırıyor ve B C'yi çağırıyorsa, üç çağrı da satır içinde genişletilir. Ancak, en yakın satır içi genişletme iki ise, yalnızca A ve B genişletilir ve C işlev çağrısı olarak kalır.

Bu pragmayı kullanmak için ayarlamalısınız `/Ob` derleyici seçeneğini 1 veya 2. Bu pragma kullanılarak ayarlanan derinlik, pragmadan sonraki ilk işlev çağrısında etkin hale gelir.

Satır içi derinlik, genişletme sırasında azaltılabilir, ancak artırılmaz. Satır içi derinliği altıysa ve genişleme sırasında önişlemci karşılaştığında bir **inline_depth** pragma sekiz derinlik değerini altı olarak kalır.

**İnline_depth** pragma ile işaretlenen işlevler üzerinde hiçbir etkisi `__forceinline`.

> [!NOTE]
> Özyinelemeli işlevler, satır içinde en fazla 16 çağrılık bir derinlikle değiştirilebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)