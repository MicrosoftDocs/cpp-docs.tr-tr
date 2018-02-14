---
title: "Uzaktan otomasyonda güvenlik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AllowRemoteActivation [MFC]
- Remote Automation [MFC], security
- activating objects [MFC]
- security [MFC]
- Automation objects [MFC], security options
- object activation [MFC]
- security [MFC], Remote Automation
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e535fac6330d6268629e8e3681fec47c7b0d65d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="security-in-remote-automation"></a>Uzaktan Otomasyonda Güvenlik
Uzak Otomasyon temel sunucu uygulama yazıcısı (veya bunun yerine, yönetici) belirli bir nesneyi uzaktan nasıl etkinleştirilebilir belirtmek izin vermek için güvenlik düzeyini destekler. Belirli bir sistemde tüm otomasyon nesneleri "Uzaktan etkinleştirmeye izin vermeyecek şekilde" veya "Uzaktan etkinleştirmeye izin vermek için" genel olarak ayarlanmış olabilir. Buna ek olarak ve daha sık ayrı ayrı nesneleri aşağıdakiler gibi özelliklerinden verilebilir. Uzaktan otomasyon kullanan bir anahtar her nesnenin kayıt defteri ayarlarını **AllowRemoteActivation**, belirli bir sunucuda uzaktan etkinleştirilebilir olup olmadığını belirlemek için. Bu mod yükleyebilecek ayarları kullanırsanız, kayıt defterinde her nesne bu anahtar ardından atanmış ve her biri ayrı ayrı durumu "Evet" veya uygun olarak "Hayır" şekilde ayarlanmış olmalıdır.  
  
 Windows NT veya Windows 2000 server sistemi çalışıyorsa, alternatif bir form güvenlik izin verilir. Bu durumda, uzak Otomasyon NT erişim denetimi listesi (ACL) hangi kullanıcı veya grup veya kullanıcı gruplarına belirli bir sunucuda uzaktan etkinleştirebilir belirlemek için kullanır.  
  
 Güvenlik seçenekleri nesnenin tamamı için geçerli olduğunu unutmayın; Bu nesne üzerinde ayrı özellikler ve yöntemler veya belirli bir arabirim öznitelikleri ayarlamak mümkün değildir.  
  
 Uzak Otomasyon bağlantı (RAC) Yöneticisi üzerinden tüm güvenlik seçeneklerini ayarlayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzak Otomasyon](../mfc/remote-automation.md)

