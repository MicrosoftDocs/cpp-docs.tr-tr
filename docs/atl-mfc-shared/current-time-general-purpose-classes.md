---
title: 'Geçerli saat: Genel amaçlı sınıfları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec71cf76f859457aa76e69b57b58db3940e974da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354601"
---
# <a name="current-time-general-purpose-classes"></a>Geçerli saat: Genel amaçlı sınıfları
Aşağıdaki yordam nasıl oluşturulacağını gösterir bir `CTime` nesne ve geçerli saati ile başlatılamadı.  
  
#### <a name="to-get-the-current-time"></a>Geçerli saati almak için  
  
1.  Allocate bir `CTime` nesnesi, aşağıdaki gibi:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Başlatılmamış `CTime` nesneleri için geçerli bir saat başlatılmadı.  
  
2.  Çağrı `CTime::GetCurrentTime` işletim sisteminden geçerli saati alınacak işlev. Bu işlev döndüren bir `CTime` değerini ayarlamak için kullanılan nesne `CTime`aşağıdaki gibi:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     Bu yana `GetCurrentTime` statik üye işlevinden olan `CTime` sınıfı, sınıf ve kapsam çözümü işleci adını adıyla nitelemeniz gerekir (`::`), `CTime::GetCurrentTime()`.  
  
 Elbette, ana hatlarıyla iki adımı daha önce tek bir program ifadesine gibi birleştirilir:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve Saat: Genel Amaçlı Sınıflar](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



