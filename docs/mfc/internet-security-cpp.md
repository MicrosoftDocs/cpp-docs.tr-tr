---
title: "Internet güvenliği (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 879078481cde75841cf180329ef67a6badfa4b61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="internet-security-c"></a>Internet Güvenliği (C++)
Kod güvenliği bir Internet uygulamaları kullanıcılarının ve geliştiriciler için başlıca sorunudur. Riskleri vardır: kötü amaçlı kod, üzerinde oynanmış kodu ve bilinmeyen siteleri veya yazarları koddan.  
  
 Internet için geliştirirken güvenlik temel iki yaklaşım vardır. İlk "korumalı alan." olarak adlandırılır Bu yaklaşım, uygulamanın belirli bir API kümesi kısıtlanmış ve bir programı bir kullanıcının bilgisayarında verileri nerede yok edebilir dosya g/ç gibi potansiyel olarak tehlikeli olabilecek olanlar dışında tutulması. İkincisi, dijital imzalar kullanılarak uygulanır. Bu yaklaşım için "shrinkwrap" Internet'te denir. Kod doğrulanır ve özel anahtarı/ortak anahtar teknolojisini kullanarak imzalanmış. Kod çalıştırmadan önce dijital imzası kodun bilinen bir kimliği doğrulanmış kaynaktan olduğunu ve oturumunuz kapatıldı beri'nın kodunu değiştirilmediğini emin olmak için doğrulanır.  
  
 İlk durumda uygulama herhangi bir zarar ne yapacağını ve uygulama kökeni güven güven. İkinci, dijital imzalar orijinalliğini doğrulamak için kullanılır. Dijital imza tanımlamak ve kod yayımcısı hakkındaki ayrıntıları sağlamak için kullanılan bir endüstri standardıdır. Kendi teknolojisi RSA ve X.509 dahil olmak üzere standartlarını temel alır. Tarayıcılar, genellikle kullanıcıların bunlar indirin ve bilinmeyen kaynak kodu çalıştırmak isteyip istemediğinizi seçin izin verin.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)

