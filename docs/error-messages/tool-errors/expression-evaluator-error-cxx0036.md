---
title: İfade Değerlendirici Hatası CXX0036
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: 164fd9ee00071e218e5bb4f3ab00febc618725a7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195506"
---
# <a name="expression-evaluator-error-cxx0036"></a>İfade Değerlendirici Hatası CXX0036

Hatalı bağlam {...} belirtim

Bu ileti, bağlam işlecinin ( **{}** ) kullanımıyla ilgili birkaç hata ile oluşturulabilir.

- Bağlam işlecinin sözdizimi ( **{}** ) yanlış olarak verildi.

   Bağlam işlecinin sözdizimi şöyledir:

     {*Function*,*module*,*DLL*} *ifade*

   Bu, *ifadesinin*bağlamını belirtir. Bağlam operatörü, tür atama ile aynı önceliğe ve kullanıma sahiptir.

   Sondaki virgüller atlanabilir. Herhangi bir *işlev*, *Modül*veya *DLL* , sabit bir virgül içeriyorsa, tüm adı parantez içine almalısınız.

- İşlev adı yanlış yazılmış veya belirtilen modülde veya dinamik bağlantı kitaplığında yok.

   C, büyük/küçük harfe duyarlı bir dil olduğundan, kaynak üzerinde tanımlandığı için *işlevin* tam büyük/küçük harf olarak verilmesi gerekir.

- Modül veya DLL bulunamadı.

   Belirtilen modülün veya DLL dosyasının tam yol adını denetleyin.

Bu hata CAN0036 ile aynıdır.
