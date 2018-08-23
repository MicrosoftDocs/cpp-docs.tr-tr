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
ms.openlocfilehash: 1a208e85418f362bfa698055ba6b3b403c21bce0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610876"
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

[İletişim Kutusu Denetimleri için Üye Değişkenleri Tanımlama](../windows/defining-member-variables-for-dialog-controls.md)  
[Kullanıcı Arabirimi Nesneleri ile İlişkili İleti Türleri](../mfc/reference/message-types-associated-with-user-interface-objects.md)  
[İleti İşleyicisini Düzenleme](../mfc/reference/editing-a-message-handler.md)  
[Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)  
[Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)  
[Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)