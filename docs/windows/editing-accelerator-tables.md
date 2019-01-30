---
title: (C++) Hızlandırıcı tablolarını düzenleme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
- searching, in accelarator tables
- accelerator tables [C++], finding entries
- accelerator tables [C++], adding entries
- New Accelerator command
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
- accelerator tables [C++], copying entries
- rc files [C++], moving an accelerator table entry
- .rc files [C++], moving accelerator table entries
- accelerator tables [C++], moving entries
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: 56e24efb-d06b-4ed9-8915-1f99f725e247
ms.openlocfilehash: dfa0c26132378bcbe8a7f5203351134d91746aa7
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232181"
---
# <a name="editing-accelerator-tables-c"></a>(C++) Hızlandırıcı tablolarını düzenleme

Bir C++ projesinde, doğrudan yerinde düzenlemeyle Hızlandırıcı tablosunu düzenleyebilirsiniz **hızlandırıcı** Düzenleyici.

Standart özellik sayfalarının kullanımı için aşağıdaki yordamlara bakın, ancak aynı sonucu yerinde düzenleme ve özellik sayfası yöntemi vardır. Özellik sayfaları veya yerinde düzenlemeyi kullanarak yapılan değişiklikler hemen Hızlandırıcı tablosunda yansıtılır.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="to-edit-in-an-accelerator-table"></a>Hızlandırıcı tablosunu düzenleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir giriş tablosunda seçin ve yerinde düzenlemeyi etkinleştirmek için seçin.

1. Açılan birleşik giriş kutusundan seçin veya değişiklik yerinde yazın.

   - İçin [kimliği](id-property.md)listesinden veya düzenlemek için türü seçin.

   - İçin [değiştiricisi](../windows/accelerator-modifier-property.md)listeden seçin.

   - İçin [anahtar](../windows/accelerator-key-property.md)listesinden veya düzenlemek için türü seçin.

   - İçin [türü](../windows/accelerator-type-property.md)seçin **ASCII** veya **VIRTKEY'e** listeden.

## <a name="to-find-an-entry-in-an-open-accelerator-table"></a>Açık Hızlandırıcı tablosunda giriş aramak için

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir sütunun içeriğine alfabetik olarak sıralamak için sütun head seçin. Örneğin, **kimliği** Hızlandırıcı tablonuzdaki tüm kimlikleri alfabetik olarak görüntülenecek.

Listenin tarama ve girişini bulun.

## <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosunu giriş ekleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tablosu içinde sağ tıklatın ve seçin **yeni hızlandırıcı** kısayol menüsünden veya tablonun alt kısmındaki boş satır girişi seçin.

1. Seçin bir [kimliği](id-property.md) kimliği aşağı açılan listeden kutusuna veya yeni bir kimliği yazın **kimliği** kutusu.

1. Türü [anahtarı](../windows/accelerator-key-property.md) bir Hızlandırıcı veya sağ tıklayarak kullanın ve isteyip **sonraki anahtarı yazılan** bir tuş bileşimi ayarlamak için kısayol menüsünden ( **sonraki anahtarı yazılan** komutu Ayrıca kullanılabilir **Düzenle** menü).

1. Değişiklik [değiştiricisi](../windows/accelerator-modifier-property.md) ve [türü](../windows/accelerator-type-property.md), gerekirse.

1. Tuşuna **girin**.

   > [!NOTE]
   > Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Birkaç tuş bileşimleri aynı Kimliğine sahip hiçbir olumsuz etkisi, örneğin, atanan olabilir **Ctrl** + **P** ve **F8** ID_PRINT için her ikisi de atanabilir. Ancak, birden fazla kimliği çalışmaz, örneğin, atanan bir tuş bileşimi sahip **Ctrl** + **Z** ID_SPELL_CHECK ve ID_THESAURUS atanmış.

## <a name="to-delete-an-entry-from-an-accelerator-table"></a>Hızlandırıcı tablosundan giriş silme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Silmek istediğiniz girişini seçin. (Basılı **Ctrl** veya **Shift** birden çok girişi seçmek için seçme tuşunu.)

1. Sağ tıklatın ve seçin **Sil** kısayol menüsünden (veya **Sil** gelen **Düzenle** menü).

\- veya -

- Tuşuna **Sil** anahtarı.

## <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>Hızlandırıcı tablosu girişini başka bir kaynak betik dosyasına taşınacak veya kopyalanacak

1. Hızlandırıcı tablolarını, hem kaynak kod dosyalarını açın.

1. Taşımak istediğiniz girişini seçin.

1. Gelen **Düzenle** menüsünde seçin **kopyalama** veya **Kes**.

1. Hedef kaynak kod dosyasında bir giriş seçin.

1. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   > [!NOTE]
   > Ayrıca, kopyalama ve yapıştırma için kısayol tuşlarını kullanabilirsiniz.

## <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Birden çok hızlandırma tuşunun özelliklerini değiştirme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tuşları basılı tutarak değiştirmek istediğiniz seçin **Ctrl** anahtar her birini seçin.

1. Git [Özellikler penceresi](/visualstudio/ide/reference/properties-window) tüm paylaşmak için seçilen Hızlandırıcılar istediğiniz değerleri yazın.

   > [!NOTE]
   > Her değiştiricisi değer bir Boolean özelliği olarak görünür **özellikleri** penceresi. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) değerini **özellikleri** penceresinde Hızlandırıcı tablosunu işler yeni değiştiricisini ek olarak, önceden var olan tüm değiştiriciler. Herhangi bir değiştirici değeri ayarlarsanız, bu nedenle, her hızlandırıcının aynı paylaşımları sağlamak için bunların tümünü ayarlamak ihtiyacınız olacak **değiştiricisi** ayarları.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)
