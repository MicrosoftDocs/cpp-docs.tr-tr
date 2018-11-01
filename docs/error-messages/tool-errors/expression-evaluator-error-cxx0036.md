---
title: İfade Değerlendirici Hatası CXX0036
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: d7961d92760cc5ac325b4bc9f187d4ee2298479a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576833"
---
# <a name="expression-evaluator-error-cxx0036"></a>İfade Değerlendirici Hatası CXX0036

hatalı bağlam {...} belirtim

Bu ileti, şu içerik işlecini kullanımında çeşitli hatalardan birini tarafından oluşturulabilir (**{}**).

- İçerik işleci sözdizimini (**{}**) hatalı durumda verildi.

   Şu içerik işlecini sözdizimi aşağıdaki gibidir:

     {*işlevi*,*Modülü*,*dll*}*ifadesi*

   Bu bağlamı belirtir *ifade*. Şu içerik işlecini bir cast türünü aynı öncelik ve kullanım vardır.

   Virgül sondaki atlanabilir. Varsa *işlevi*, *Modülü*, veya *dll* sabit bir virgül içeren tüm adı parantez içine almalısınız.

- İşlev adı yanlış yazılmış veya belirtilen modül veya dinamik bağlantı kitaplığı yok.

   C büyük küçük harfe duyarlı bir dil olduğundan *işlevi* kaynağında tanımlanan tam durumda verilmelidir.

- Modül veya DLL bulunamadı.

   Belirtilen modül veya DLL tam yol adını kontrol edin.

Bu hata için CAN0036 aynıdır.