---
title: ActiveX denetimi Ekle iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.insertActiveXControls
dev_langs:
- C++
helpviewer_keywords:
- Insert ActiveX Control dialog box
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0cf6c5efb0c7613c1332ce05483bd311b037a9b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194488"
---
# <a name="insert-activex-control-dialog-box"></a>ActiveX Denetimi Ekle İletişim Kutusu

Bu iletişim kutusu sayesinde [, iletişim kutusuna ActiveX denetimleri ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md) kullanırken [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).

### <a name="activex-control"></a>ActiveX denetimi

ActiveX denetimleri listesini görüntüler. Bu iletişim kutusundan bir denetim ekleme, bir sarmalayıcı sınıfı oluşturmaz. Sarmalayıcı sınıf ihtiyacınız varsa, [sınıf görünümü](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) oluşturmak için (daha fazla bilgi için [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)). Bu iletişim kutusunda bir ActiveX denetimi görünmüyorsa, satıcının yönergelerine göre denetim yükleme deneyin.

### <a name="path"></a>Yol

ActiveX denetimi içinde bulunan dosyayı görüntüler.

Denetimlerinde yerleştirebilirsiniz **araç kutusu** penceresi kolay erişim için. Daha fazla bilgi için [özelleştirme araç kutusu iletişim kutusunda](https://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi Sekmesi, Araç Kutusu](../windows/dialog-editor-tab-toolbox.md)  
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)