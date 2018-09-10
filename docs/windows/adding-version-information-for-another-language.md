---
title: Başka bir dil (C++) için sürüm bilgileri ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bf01f1d4b1c687ed919b94f651ef7ccf4b0bf45d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313461"
---
# <a name="adding-version-information-for-another-language-c"></a>Başka bir dil (C++) için sürüm bilgileri ekleme

### <a name="to-add-version-information-for-another-language-new-info-block"></a>(Yeni bilgi bloğu) başka bir dil için sürüm bilgileri ekleme

1. Sürüm bilgileri kaynağında çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde sürüm bilgileri tabloya sağ tıklayıp seçin **yeni sürüm bilgi bloğu** kısayol menüsünden.

   Bu komut bir ek bilgi bloğu geçerli sürüm bilgileri kaynağında için ekler ve karşılık gelen özelliklerini açar [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

3. İçinde **özellikleri** penceresinde ilgili dili seçin ve karakter kümesi için yeni bir blok.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sürüm Bilgileri Düzenleyicisi](../windows/version-information-editor.md)  
[Sürüm bilgileri (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)