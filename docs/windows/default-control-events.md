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
ms.openlocfilehash: a50b0deeb525481afb1da7221689924c41930bff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="default-control-events"></a>Varsayılan Denetim Olayları
Aşağıdaki denetim adlarının eşlik eden varsayılan olayları vardır:  
  
|Denetim adı|Varsayılan olay|  
|------------------|-------------------|  
|Animasyon ekleme|**ACN_START**|  
|Onay kutusu|**BN_CLICKED**|  
|Birleşik giriş kutusu|**CBN_SELCHANGE**|  
|Özel|**TTN_GETDISPINFO**|  
|Tarih Saat Seçici|**DTN_DATETIMECHANGE**|  
|Düzenleme kutusu|**EN_CHANGE**|  
|Grup kutusu|(Uygulanamaz)|  
|Kısayol tuşu|**NM_OUTOFMEMORY**|  
|IP adresi|**IPN_FIELDCHANGED**|  
|List|**LVN_ITEMCHANGE**|  
|Liste kutusu|**LBN_SELCHANGE**|  
|Ay takvim|**MCN_SELCHANGE**|  
|Resim denetimi|(Uygulanamaz)|  
|İlerleme durumu|**NM_CUSTOMDRAW**|  
|Düğme|**BN_CLICKED**|  
|Radyo düğmesi|**BN_CLICKED**|  
|Zengin düzenleme|**EN_CHANGE**|  
|Kaydırma çubuğu|**NM_THEMECHANGED**|  
|Kaydırıcı|**NM_CUSTOMDRAW**|  
|Döndürme|**UDN_DELTAPOS**|  
|Statik metin|(Uygulanamaz)|  
|Tab|**TCN_SELCHANGE**|  
|Ağaç|**TVN_SELCHANGE**|  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu denetimleri için üye değişkenleri tanımlama](../windows/defining-member-variables-for-dialog-controls.md)   
 [Kullanıcı arabirimi nesneleri ile ilişkili ileti türleri](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [İleti işleyicisini düzenleme](../mfc/reference/editing-a-message-handler.md)   
 [Yansımış bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Yeni Denetim sınıfınıza dayalı değişken bildirme](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)

