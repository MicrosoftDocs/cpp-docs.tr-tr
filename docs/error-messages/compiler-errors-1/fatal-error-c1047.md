---
description: 'Daha fazla bilgi edinin: önemli hata C1047'
title: Önemli hata C1047
ms.date: 02/17/2021
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.openlocfilehash: f22d7c7591e2c2c477d09f1637641cc351eeafb5
ms.sourcegitcommit: 5efc34c2b98d4d0d3e41aec38b213f062c19d078
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2021
ms.locfileid: "101844487"
---
# <a name="fatal-error-c1047"></a>Önemli hata C1047

> '*Filename*' nesne veya kitaplık dosyası diğer nesnelerden daha eski bir derleyici ile oluşturulmuş; eski nesneleri ve kitaplıkları yeniden oluşturma

Bu hata, projenizi oluşturmak için derleyicinin yeni bir sürümünü kullanırsanız, ancak var olan nesne dosyalarını veya kitaplıklarını temiz bir şekilde yeniden oluşturmanız durumunda meydana gelebilir.

## <a name="remarks"></a>Açıklamalar

C1047, **`/GL`** **`/LTCG`** Visual Studio C/C++ derleyici araç takımının farklı sürümlerinde veya kullanılarak oluşturulan nesne dosyaları ya da kitaplıklar birbirine bağlandığında oluşur. Örneğin, Visual Studio **`/LTCG`** 2019 sürüm 16,7 kullanılarak oluşturulan bir kitaplığı, Visual studio 2019 sürüm 16,8 kullanılarak oluşturulmuş bir uygulamaya bağlayamazsınız. Nesne ve kitaplıkları derlemek için kullanılan araç takımının büyük ve küçük güncelleştirme numaraları tam olarak eşleşmelidir.

C1047 çözümlemek için, araç takımının aynı sürümünü kullanarak tüm nesne dosyalarını veya kitaplıklarını yeniden derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[`/GL` (Tüm program Iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)\
[`/LTCG` (Bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)\
[C++ ikili uyumluluğu 2015-2019](../../porting/binary-compat-2015-2017.md)
