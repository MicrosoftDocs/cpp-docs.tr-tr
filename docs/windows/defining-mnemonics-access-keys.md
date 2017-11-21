---
title: "Anımsatıcıları (erişim tuşları) tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f19e255b2c8b63558dfe178ccfd7a23f8992861
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-mnemonics-access-keys"></a>Anımsatıcıları Tanımlama (Erişim Tuşları)
Normalde, klavye kullanıcıların giriş odağını bir denetimden başka bir iletişim kutusu ile sekme veya ok tuşları taşıyın. Ancak, tek bir tuşuna basarak bir denetim seçmek kullanıcılara bir erişim anahtarı (anımsatıcı veya unutmayın kolay adı) tanımlayabilirsiniz.  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Görünür resim yazısı (düğmeler, onay kutularını ve radyo düğmeleri) olan bir denetim için erişim anahtarı tanımlamak için  
  
1.  İletişim kutusu üzerinde denetimi seçin.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), **resim yazısı** özelliği, ve işareti yazarak denetim için yeni bir ad yazın (**&**) olarak istediğiniz harfini önünde Bu denetim için erişim anahtarı. Örneğin, `&Radio1`.  
  
3.  Tuşuna **girin**.  
  
     Örneğin, erişim anahtarı belirtmek için görüntülenen başlıkta altı çizili görünen **R**adio1.  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Görünür resim yazısı olmadan bir denetim için erişim anahtarı tanımlamak için  
  
1.  Denetim için bir başlığı kullanarak yapmak bir **statik metin** denetim [araç](/visualstudio/ide/reference/toolbox).  
  
2.  Statik metin resim yazısı ampersan yazın (**&**) erişim tuşu olarak istediğiniz harfini önünde.  
  
3.  Statik metin denetimini hemen sekme sırası etiketler denetim önündeki emin olun.  
  
 Tüm erişim anahtarları bir iletişim kutusu içinde benzersiz olmalıdır.  
  
#### <a name="to-check-for-duplicate-access-keys"></a>Yinelenen erişim anahtarlarını denetlemek için  
  
1.  Üzerinde **biçimi** menüsünde tıklatın **anımsatıcıları kontrol**.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimleri](../mfc/controls-mfc.md)

