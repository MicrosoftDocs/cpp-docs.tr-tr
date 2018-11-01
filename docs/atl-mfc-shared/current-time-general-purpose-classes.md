---
title: 'Geçerli zaman: Genel amaçlı sınıflar'
ms.date: 11/04/2016
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
ms.openlocfilehash: e883a47243feb7ad1555748ffdda9b8ae9594644
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539262"
---
# <a name="current-time-general-purpose-classes"></a>Geçerli zaman: Genel amaçlı sınıflar

Aşağıdaki yordam nasıl oluşturulacağını gösterir. bir `CTime` nesne ve geçerli saati ile başlatır.

### <a name="to-get-the-current-time"></a>Geçerli zamanı almak için

1. Ayırma bir `CTime` nesnesini şu şekilde:

   [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]

   > [!NOTE]
   > Başlatılmamış `CTime` nesneler için geçerli bir saat başlatılmadı.

1. Çağrı `CTime::GetCurrentTime` işletim sisteminden geçerli zamanı almak için işlevi. Bu işlev döndürür bir `CTime` değerini ayarlamak için kullanılan nesne `CTime`gibi:

   [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]

   Bu yana `GetCurrentTime` bir statik üye işlev olduğu `CTime` sınıf adı sınıf ve kapsam çözümleme işleci adıyla nitelemeniz gerekir (`::`), `CTime::GetCurrentTime()`.

Elbette, iki ana hatlarıyla belirtilen adımları daha önce tek bir program ifadesi şu şekilde birleştirilir:

[!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]
