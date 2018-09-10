---
title: Bir dize kaynağı (C++) biçimlendirme veya özel karakterler ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bf67723f516e0c5b1bf9931d7f53d36907fca86
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313396"
---
# <a name="adding-formatting-or-special-characters-to-a-string-resource-c"></a>Bir dize kaynağı (C++) biçimlendirme veya özel karakterler ekleme

### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Dizeye biçimlendirme veya özel karakterler ekleme

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Değiştirmek istediğiniz dizeyi seçin.

3. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), herhangi bir standart kaçış dizileri aşağıda listelenen metinde ekleme **açıklamalı alt yazı** kutusu ve ENTER tuşuna **Enter**.

   |Bu alınacağı|Bunu yazın|
   |-----------------|---------------|
   |Yeni satır|\n|
   |satır başı|\r|
   |Tab|\t|
   |Ters eğik çizgi (\\)|\\\|
   |ASCII karakteri|\ddd (sekizlik gösterim)|
   |Uyarı (zil)|\a|

> [!NOTE]
> **Dize** Düzenleyicisi kaçan ASCI karakter kümesini desteklemiyor. Yalnızca yukarıda listelenen kullanabilirsiniz.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)  