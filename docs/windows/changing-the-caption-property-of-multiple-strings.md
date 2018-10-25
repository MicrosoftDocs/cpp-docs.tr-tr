---
title: Birden çok dize kaynakları (C++) resim yazısı özelliğini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 459114678352004293b425ba7cdff39d15d084b1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057757"
---
# <a name="changing-the-caption-property-of-multiple-string-resources-c"></a>Birden çok dize kaynakları (C++) resim yazısı özelliğini değiştirme

Aşağıdaki yordam, birden çok dizenin resim yazısı özelliğini değiştirme işlemini göstermektedir.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>Birden çok dizenin resim yazısı özelliğini değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Basılı tutarak değiştirmek istediğiniz dizeleri seçin **Ctrl** anahtar her birini tıklatın.

3. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), değiştirmek istediğiniz özelliği için yeni bir değer yazın.

4. Tuşuna **girin**.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)