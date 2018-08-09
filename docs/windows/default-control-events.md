---
title: Varsayılan denetim olayları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls, events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d9ffea9bf6ffbbc6d34e130b2031297ff1ef3f99
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649626"
---
# <a name="default-control-events"></a>Varsayılan Denetim Olayları
Aşağıdaki denetim adları, eşlik eden varsayılan olayları vardır:  
  
|Denetim adı|Varsayılan olay|  
|------------------|-------------------|  
|Animasyon ekleme|ACN_START|  
|Onay kutusu|BN_CLICKED|  
|Birleşik giriş kutusu|CBN_SELCHANGE|  
|Özel|TTN_GETDISPINFO|  
|Tarih Saat Seçici|DTN_DATETIMECHANGE|  
|Düzenleme kutusu|EN_CHANGE|  
|Grup kutusu|(Uygulanamaz)|  
|Kısayol tuşu|NM_OUTOFMEMORY|  
|IP adresi|IPN_FIELDCHANGED|  
|List|LVN_ITEMCHANGE|  
|Liste kutusu|LBN_SELCHANGE|  
|Aylık takvim|MCN_SELCHANGE|  
|Resim denetimi|(Uygulanamaz)|  
|İlerleme durumu|NM_CUSTOMDRAW|  
|İtme düğmesi|BN_CLICKED|  
|Radyo düğmesi|BN_CLICKED|  
|Zengin düzenleme|EN_CHANGE|  
|Kaydırma çubuğu|NM_THEMECHANGED|  
|Kaydırıcı|NM_CUSTOMDRAW|  
|Döndürme|UDN_DELTAPOS|  
|Statik metin|(Uygulanamaz)|  
|Tab|TCN_SELCHANGE|  
|Ağaç|TVN_SELCHANGE|  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu denetimleri için üye değişkenleri tanımlama](../windows/defining-member-variables-for-dialog-controls.md)   
 [Kullanıcı arabirimi nesneleri ile ilişkili ileti türleri](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [İleti işleyicisini düzenleme](../mfc/reference/editing-a-message-handler.md)   
 [Yansımış bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Yeni Denetim sınıfınıza dayalı değişken bildirme](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)