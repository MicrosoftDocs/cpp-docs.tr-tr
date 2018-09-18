---
title: İfade değerlendirici hatası CXX0036 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2d82a1254a11dbda3164ea1c350dc14e2b1a122
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050118"
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