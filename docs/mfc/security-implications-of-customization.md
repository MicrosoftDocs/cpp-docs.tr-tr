---
title: "Özelleştirmenin güvenlikle ilgili etkileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b408b4595e95016323d2b43f1ed51fc6e2e6d244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="security-implications-of-customization"></a>Özelleştirmenin Güvenlikle İlgili Etkileri
Bu konu, olası bir güvenlik zayıflık MFC'de açıklar.  
  
## <a name="potential-security-weakness"></a>Olası güvenlik zayıflık  
 MFC sağlayan kullanıcı bir uygulama kullanıcı arabirimi, örneğin, düğmeler ve simgeler görünümünü görünümünü özelleştirebilirsiniz. MFC Kabuk komutları yürütmek kullanıcı olanak sağlayan kullanıcı tanımlı araçlar da destekler. Bir güvenlik açığı, uygulamanın özelleştirilmiş ayarları kayıt kullanıcı profiline kaydedilir doğurur. Kayıt defteri erişebilen herkes bu ayarları düzenleyin ve uygulama görünüşünü veya davranışını değiştirin. Örneğin, bilgisayarda yönetici rasgele programlar (bile bir ağ paylaşımından) yürütmek kullanıcının uygulama neden olan bir kullanıcının kimliğine bürünme.  
  
## <a name="workarounds"></a>Geçici Çözümler  
 Herhangi bir kayıt defteri güvenlik açıklarını kapatmak için bu üç yolla öneririz:  
  
-   Var. depolanan verileri şifrele  
  
-   Veri dosyasında bir güvenli yerine kayıt defterinde depolar.  
  
     Bu ilk iki yoldan biriyle gerçekleştirmek için öğesinden bir sınıf türetin [CSettingsStore sınıfı](../mfc/reference/csettingsstore-class.md) ve şifreleme veya kayıt defteri dışında depolama uygulamak için yöntemlerini geçersiz kılar.  
  
-   Özelleştirmeleri, uygulamanızda da devre dışı bırakabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC için Özelleştirme](../mfc/customization-for-mfc.md)

