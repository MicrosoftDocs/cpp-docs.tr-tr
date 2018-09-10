---
title: 'Nasıl yapılır: bir kaynak (C++) oluştur | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c12357acf3369192248784fc6593c9b5b91b863
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316789"
---
# <a name="how-to-create-a-resource"></a>Nasıl Yapılır: Kaynak Oluşturma

> [!NOTE]
> **Kaynak görünümü** Express sürümlerinde desteklenmez.

### <a name="to-create-a-new-resource-in-resource-view"></a>Kaynak Görünümü'nde yeni bir kaynak oluşturmak için

1. Bir .rc dosyasında odaklanarak [kaynak görünümü](../windows/resource-view-window.md), tıklayın **Düzenle** menü ve **kaynak Ekle** (veya .rc dosyasına sağ tıklayın **KaynakGörünümü** ve **kaynak Ekle** kısayol menüsünden).

   > [!NOTE] 
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.

### <a name="to-create-a-new-resource-in-solution-explorer"></a>Çözüm Gezgini içinde yeni bir kaynak oluşturmak için

1. İçinde **Çözüm Gezgini**, proje klasörü sağ tıklatın ve seçin **Ekle**, ardından **kaynak Ekle** kısayol menüsünde.

   Projenizde bir .rc dosyası yoksa, bu adımı oluşturur. Sonra belirli kaynak türlerine yeni .rc dosyasına eklemek için bu adımı yineleyebilirsiniz.

2. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.

### <a name="to-create-a-new-resource-in-class-view"></a>Sınıf Görünümü'nde yeni bir kaynak oluşturmak için

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)sınıfınıza sağ tıklatın ve seçin **Ekle**, ardından **kaynak Ekle** kısayol menüsünden.

2. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.

### <a name="to-create-a-new-resource-from-the-project-menu"></a>Proje menüsünden Yeni bir kaynak oluşturmak için

1. Gelen **proje** menüsünde seçin **kaynak Ekle**.

Yeni bir kaynak oluşturduğunuzda, Visual C++ benzersiz bir ad, örneğin atar `IDD_Dialog1`. Bu kaynak kimliği için ilişkili kaynak Düzenleyicisi'ni veya kaynak özellikleri düzenleyerek özelleştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

Yeni bir varsayılan kaynak (bir şablona dayalı olmayan bir kaynak) veya sonra desenli bir kaynak olarak bir kaynak oluşturmak bir [şablon](../windows/how-to-use-resource-templates.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Kaynak Ekle İletişim Kutusu](../windows/add-resource-dialog-box.md)