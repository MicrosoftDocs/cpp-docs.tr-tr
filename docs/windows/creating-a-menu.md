---
title: Menü (C++) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59689abec68fc6cff2a742bd4db97b58cd023af1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316269"
---
# <a name="creating-a-menu-c"></a>Menü (C++) oluşturma

> [!NOTE]
> **Kaynak penceresi** Express sürümlerinde kullanılamaz.

### <a name="to-create-a-standard-menu"></a>Standart menü oluşturmak için

1. Gelen **görünümü** menüsünde tıklatın **kaynak görünümü** ve ardından sağ tıklayarak **menü** başlık ve seçin **kaynak Ekle**. Seçin **menü**.

2. Seçin **yeni öğe** menü çubuğundaki kutusuna ("Buraya türü" içeren dikdörtgen).

   ![Menü Düzenleyicisi'nde yeni bir öğe kutusu](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")  
Yeni öğe kutusu

3. Yeni menünüzde, örneğin, "File" için bir ad yazın.

   Her ikisinde de, yazdığınız metni görünür **menü** Düzenleyicisi ve **açıklamalı alt yazı** kutusunda [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüzde özelliklerini düzenleyebilirsiniz.

   Menü çubuğunda yeni menünüzde bir adı verilen sonra yeni öğe kutusunu (başka bir menü eklemenize izin vermek için) sağa kaydırır ve menü komutları ekleyebilmek için ilk menünüzün başka bir yeni öğe kutusu açılır.

   ![Genişletilmiş yeni öğe kutusunda](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")  
Menü adını yazdıktan sonra yeni öğe kutusu odaklanılan kaydırılacağı uzaklık.

   > [!NOTE]
   > Menü çubuğunda bir tek öğesi menüsü oluşturmak için **açılan** özelliğini **False**.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)