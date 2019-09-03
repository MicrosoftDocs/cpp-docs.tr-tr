---
title: inline_depth pragması
ms.date: 08/29/2019
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: be57178280e278683b85db1413ff5724b5260aef
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220976"
---
# <a name="inline_depth-pragma"></a>inline_depth pragması

Satır içi buluşsal arama derinliğini belirtir. Çağrı grafiğinde belirtilen değerden büyük bir derinlikte bulunan işlevler satır içine alınmadı.

## <a name="syntax"></a>Sözdizimi

> **#pragma inline_depth (** [ *n* ] **)**

## <a name="remarks"></a>Açıklamalar

Bu pragma, [satır içi](../cpp/inline-functions-cpp.md) ve [__inline](../cpp/inline-functions-cpp.md)olarak işaretlenen işlevlerin listesini denetler veya `/Ob` seçeneğinin altında otomatik olarak satır içine alır.

*n* , 0 ile 255 arasında bir değer olabilir; burada 255, çağrı grafiğinde sınırsız derinliğe yol açabilir. 0 değeri satır içi genişletmeyi engeller. *N* belirtilmediğinde, varsayılan 254 değeri kullanılır.

**İnline_depth** pragma, bir dizi işlev çağrısının nasıl genişletilebilecek sayısını denetler. Örneğin, satır içi derinliğin 4 olduğunu varsayalım. B çağrısı, B ve sonra C 'yi çağırırsa, üç çağrının hepsi satır içi olarak genişletilir. Ancak, en yakın satır içi derinlik genişletmesi 2 ise, yalnızca A ve B genişletilir ve C bir işlev çağrısı olarak kalır.

Bu pragmayı kullanmak için, `/Ob` derleyici seçeneğini 1 veya daha yüksek bir değere ayarlamanız gerekir. Bu pragma kullanılarak ayarlanan derinlik, pragmadan sonraki ilk işlev çağrısında etkin hale gelir.

Satır içi derinlik, genişleme sırasında azaltılabilir ancak artmaz. Satır içi derinlik 6 ise ve genişletme sırasında Önişlemci, 8 değeriyle bir **inline_depth** pragma ile karşılaştığında, derinlik 6 kalır.

**İnline_depth** pragma ile `__forceinline`işaretlenen işlevleri etkilemez.

> [!NOTE]
> Özyinelemeli işlevler, satır içinde en fazla 16 çağrılık bir derinlikle değiştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_recursion](../preprocessor/inline-recursion.md)
