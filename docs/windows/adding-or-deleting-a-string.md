---
title: Ekleyerek veya silerek bir dize kaynağı (C++) | Microsoft Docs
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
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c22990c504700ab82ae0d7542420a3f82db4d73
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314046"
---
# <a name="adding-or-deleting-a-string-resource-c"></a>Ekleyerek veya silerek bir dize kaynağı (C++)

Dize tablosu kullanarak yeni girişler hızla ekleyebilirsiniz **dize** Düzenleyici. Yeni dizeler tablonun sonuna yerleştirilir ve sonraki kullanılabilir tanımlayıcı verilir. Daha sonra düzenleyebilirsiniz **kimliği**, **değer**, veya **açıklamalı alt yazı** özelliklerinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) gerektiğinde.

**Dize** Düzenleyicisi sağlar zaten kullanımda bir kimliği kullanmayın. Bir kimliği kullanımda, zaten seçerseniz **dize** Düzenleyicisi bunu size bildirir ve ardından genel benzersiz kimliği örneğin Ata `IDS_STRING58113`.

### <a name="to-add-a-string-table-entry"></a>Dize tablo girdisi eklemek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Dize tablosu içinde sağ tıklatın ve seçin **yeni dize** kısayol menüsünden.

3. İçinde **dize** Düzenleyicisi'ni seçin bir **kimliği** kimliği aşağı açılan listesinden veya türü kimliği ile doğrudan bir yerde.

4. Düzen **değer**, gerekirse.

5. İçin bir giriş türü **açıklamalı alt yazı**.

   > [!NOTE]
   > Null dizeler Windows dize tablolarında izin verilmez. Boş bir dize olan dize tablosunda bir giriş oluşturmak, "Lütfen gir bir dize Bu tablo girişi için" için soran bir ileti alırsınız.

### <a name="to-delete-a-string-table-entry"></a>Dize tablosu girişi silmek için

1. Silmek istediğiniz girişini seçin.

2. Üzerinde **Düzenle** menüsünde tıklatın **Sil**.

\- veya -

- Sağ tıklayın ve silmek istediğiniz dizeyi **Sil** kısayol menüsünden.

\- veya -

- Tuşuna **Sil** anahtarı.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)  