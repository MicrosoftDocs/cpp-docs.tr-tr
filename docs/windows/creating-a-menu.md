---
title: Menü (C++) oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.editors.menu
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
- menus [C++], adding items
- commands [C++], adding to menus
- menu items, adding to menus
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
ms.openlocfilehash: 438480032f1fe9208e406b4ee499267e42148a48
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702810"
---
# <a name="creating-a-menu-c"></a>Menü (C++) oluşturma

> [!NOTE]
> **Kaynak penceresi** Express sürümlerinde kullanılamaz.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-create-a-standard-menu"></a>Standart menü oluşturmak için

1. Gelen **görünümü** menüsünde **kaynak görünümü** ve ardından sağ tıklayarak **menü** başlık ve seçin **kaynak Ekle**. Seçin **menü**.

1. Seçin **yeni öğe** menü çubuğundaki kutusuna ("Buraya türü" içeren dikdörtgen).

   ![Menü Düzenleyicisi'nde yeni bir öğe kutusu](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")<br/>
   Yeni öğe kutusu

1. Yeni menünüzde, örneğin, "File" için bir ad yazın.

   Her ikisinde de, yazdığınız metni görünür **menü** Düzenleyicisi ve **açıklamalı alt yazı** kutusunda [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüzde özelliklerini düzenleyebilirsiniz.

   Menü çubuğunda yeni menünüzde bir adı verilen sonra yeni öğe kutusunu (başka bir menü eklemenize izin vermek için) sağa kaydırır ve menü komutları ekleyebilmek için ilk menünüzün başka bir yeni öğe kutusu açılır.

   ![Genişletilmiş yeni öğe kutusunda](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")<br/>
   Menü adını yazdıktan sonra yeni öğe kutusu odaklanılan kaydırılacağı uzaklık.

   > [!NOTE]
   > Menü çubuğunda bir tek öğesi menüsü oluşturmak için **açılan** özelliğini **False**.

## <a name="to-insert-a-new-menu-between-existing-menus"></a>Mevcut menülerin arasına yeni menü eklemek için

Var olan bir menü adı ve ENTER tuşuna seçin **Ekle** anahtarı. **Yeni öğe** kutusu önce seçilen öğe eklenir.

   \- veya -

Menü çubuğunda sağ tıklatın ve seçin **yeni Ekle** kısayol menüsünden.

## <a name="to-add-commands-to-a-menu"></a>Bir menü komutları eklemek için

1. Bir menü oluşturun.

1. Örneğin, bir menü adı seçin **dosya**.

   Her menüsünü genişletin ve komutlar için yeni bir öğe kutusu kullanıma sunar. Örneğin, komutlar ekleyebilirsiniz **yeni**, **açık**, ve **Kapat** için bir **dosya** menüsü.

1. Yeni öğe kutuya yeni bir menü komutu için bir ad yazın.

   > [!NOTE]
   > Her ikisinde de, yazdığınız metni görünür **menü** Düzenleyicisi ve **açıklamalı alt yazı** kutusunda [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüzde özelliklerini düzenleyebilirsiniz.

   > [!TIP]
   > Menü komutunu seçmesini sağlayan bir kısayol tuşu (kısayol tuşu) tanımlayabilirsiniz. Ve işareti yazın (`&`) anımsatıcı belirtmek için bir harf önünde. Kullanıcı, harf yazarak menü komutunu seçebilir.

1. İçinde **özellikleri** menü uygulanan özellikleri komut penceresinde, seçin. Ayrıntılar için bkz [menü komut özellikleri](../windows/menu-command-properties.md).

1. İçinde **istemi** kutusunda **özellikleri** penceresinde, uygulamanızın durum çubuğunda görüntülenmesini istediğiniz istem dizesi yazın.

   Bu adım, aynı kaynak tanımlayıcısı olarak oluşturduğunuz menü komutu ile dize tablosunda bir giriş oluşturur.

   > [!NOTE]
   > Komut istemlerini ile menü öğesi için yalnızca uygulayabileceğiniz bir **açılan** özelliği **True**. Örneğin, bunlar alt menü öğeleri varsa en üst düzey menü öğeleri istemleri olabilir. Amacı, bir **istemi** ne olacağını belirtmek için bir kullanıcı menü öğesi seçtiğinde.

1. Tuşuna **Enter** menü komutu tamamlamak için.

   Ek menü komutlarını oluşturmak için yeni bir öğe kutusunda seçilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)