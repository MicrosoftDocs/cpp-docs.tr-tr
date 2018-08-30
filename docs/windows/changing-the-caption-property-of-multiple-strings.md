---
title: Birden çok dizenin resim yazısı özelliğini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor, changing properties of multiple strings
- strings [C++], changing caption property of multiple
- string editing, string tables
- string tables, changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec23396f81faf1b31f1adeb37cbb6af2854ea952
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194856"
---
# <a name="changing-the-caption-property-of-multiple-strings"></a>Birden Çok Dizenin Resim Yazısı Özelliğini Değiştirme

Aşağıdaki yordam, birden çok dizenin resim yazısı özelliğini değiştirme işlemini göstermektedir.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>Birden çok dizenin resim yazısı özelliğini değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Basılı tutarak değiştirmek istediğiniz dizeleri seçin **Ctrl** anahtar her birini tıklatın.

3. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), değiştirmek istediğiniz özelliği için yeni bir değer yazın.

4. Tuşuna **girin**.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)  