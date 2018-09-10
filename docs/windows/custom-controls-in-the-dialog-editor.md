---
title: Özel denetimler iletişim kutusu düzenleyicisindeki (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- Custom Control
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1bebca381bc9d6d644ac1aac95b902065268a9d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317712"
---
# <a name="custom-controls-in-the-dialog-editor-c"></a>Özel denetimler iletişim kutusu düzenleyicisindeki (C++)

İletişim kutusu Düzenleyicisi var olanı kullan "özel" veya "kullanıcı" iletişim kutusunda şablon denetimlerinde sağlar.

> [!NOTE]
> Bu bağlamdaki özel denetimler ActiveX denetimleri ile karıştırılmamalıdır üzeresiniz. ActiveX denetimleri, bazen OLE özel denetimler adı veriliyordu. Ayrıca, bu denetimlerin Windows kullanıcı çizimli denetimler ile karıştırmayın.

Bu işlevsellik, Windows tarafından sağlanan dışındaki denetimleri kullanmanıza olanak yöneliktir. Çalışma zamanında denetim bir pencere sınıfı (değil bir C++ sınıfı aynı) ile ilişkilidir. Aynı görevi başarmak için daha yaygın bir yolu, sizin iletişim kutunuzda statik bir denetimi gibi herhangi bir denetimi yüklemektir. Ardından çalışma zamanında, buna [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlev, bu denetim kaldırın ve kendi özel bir denetim ile değiştirin.

Bu eski bir tekniktir. Bugün bir ActiveX denetimi veya bir Windows ortak denetimi alt yazmak için çoğu durumda önerilir.

Bu özel denetimler için sınırlı olursunuz:

- Konum iletişim kutusunda ayar.

- Bir başlık yazın.

- (Uygulama kodunuzun bu ada göre denetim kaydetmelisiniz) denetimin Windows sınıfının adını belirleme.

- Denetimin stilini ayarlar bir 32 bit onaltılık değer yazarak.

- Genişletilmiş stili ayarlanıyor.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[Denetimler](../mfc/controls-mfc.md)