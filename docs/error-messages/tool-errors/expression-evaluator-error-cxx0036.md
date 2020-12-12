---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0036'
title: İfade Değerlendirici Hatası CXX0036
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: fa595c590b6e59b74d693f3b6ff777055b5af2c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338539"
---
# <a name="expression-evaluator-error-cxx0036"></a>İfade Değerlendirici Hatası CXX0036

Hatalı bağlam {...} belirtim

Bu ileti, bağlam işlecinin () kullanımıyla ilgili birkaç hata ile oluşturulabilir **{}** .

- Bağlam işlecinin () sözdizimi yanlış olarak **{}** verildi.

   Bağlam işlecinin sözdizimi şöyledir:

     {*Function*,*module*,*DLL*} *ifade*

   Bu, *ifadesinin* bağlamını belirtir. Bağlam operatörü, tür atama ile aynı önceliğe ve kullanıma sahiptir.

   Sondaki virgüller atlanabilir. Herhangi bir *işlev*, *Modül* veya *DLL* , sabit bir virgül içeriyorsa, tüm adı parantez içine almalısınız.

- İşlev adı yanlış yazılmış veya belirtilen modülde veya dinamik bağlantı kitaplığında yok.

   C, büyük/küçük harfe duyarlı bir dil olduğundan, kaynak üzerinde tanımlandığı için *işlevin* tam büyük/küçük harf olarak verilmesi gerekir.

- Modül veya DLL bulunamadı.

   Belirtilen modülün veya DLL dosyasının tam yol adını denetleyin.

Bu hata CAN0036 ile aynıdır.
