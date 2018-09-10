---
title: Bir dize kaynağı (C++) bulma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e331401a3a2a789b13bc21b76c9b1cbfcb30e33
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318506"
---
# <a name="finding-a-string-resource-c"></a>Bir dize kaynağı (C++) bulma

Dize tablosunda bir veya daha fazla dizeleri arayın ve kullanmak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) ile **dosyalarda Bul** komut (**Düzenle** menüsü) dizeleri tüm örneklerini bulmak için bir desen eşleşmesi.

### <a name="to-find-a-string-in-the-string-table"></a>Dize tablosunda bir dizeyi bulmak için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Üzerinde **Düzenle** menüsünde tıklayın **Bul ve Değiştir**, ardından **bulmak**.

3. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz string açıklamalı alt yazı metni ya da kaynak tanımlayıcı yazın.

4. Herhangi bir **Bul** seçenekleri.

5. Tıklayın **Sonrakini Bul**.

   > [!TIP]
   > Normal ifadeler dosya ararken kullanmak için **dosyalarda Bul** komutu. Sağındaki düğmeye tıklayın ya da bir desenle eşleşen normal bir ifade yazın **Aranan** normal arama listesini görüntülemek için kutusu. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu. Normal ifadeler kullanırsanız, mutlaka **kullanın: normal ifadeler** onay kutusu seçilidir.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)  