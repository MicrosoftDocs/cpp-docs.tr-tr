---
title: Bir kayıt görünümüyle çalışan rolünüzün (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
ms.openlocfilehash: 351aa2d5ce950017aa8c1b3d99c8d297a423ad9f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209007"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Bir kayıt görünümüyle çalışan rolünüzün (MFC veri erişimi)

Aşağıdaki tabloda, genellikle bir kayıt görünümü ile çalışmak için ne yapmanız gereken ve Framework 'ün sizin için ne yapması gerekenler gösterilmektedir.

### <a name="working-with-a-record-view-you-and-the-framework"></a>Kayıt görünümü ile çalışma: siz ve Framework

|Bunun için,|Framework|
|---------|-------------------|
|Formu tasarlamak için C++ görsel iletişim düzenleyicisini kullanın.|Denetimlerle bir iletişim kutusu şablon kaynağı oluşturur.|
|[CRecordView](../mfc/reference/crecordview-class.md) ve [CRecordset](../mfc/reference/crecordset-class.md)'ten türetilmiş sınıflar oluşturmak Için [MFC Uygulama Sihirbazı 'nı](../mfc/reference/database-support-mfc-application-wizard.md) kullanın.|Sınıfları sizin için yazar.|
|Kayıt görünümü denetimlerini kayıt kümesi alan veri üyelerine eşleyin.|Denetimler ve kayıt kümesi alanları arasında DDX sağlar.|
||**Taşıma**için varsayılan komut işleyicileri sağlar, **son taşı**, **İleri Taşı**ve menü ya da araç çubuğu düğmelerinden önceki komutları **taşır** .|
||Veri kaynağındaki değişiklikleri güncelleştirir.|
|Seçim Liste kutularını veya Birleşik giriş kutularını ya da ikinci bir kayıt kümesinden alınan verileri içeren diğer denetimleri dolduracak kodu yazın.||
|Seçim Özel doğrulamalar için kod yazın.||
|Seçim Kayıt eklemek veya silmek için kod yazın.||

Form tabanlı programlama, bir veritabanıyla çalışmaya yönelik yalnızca bir yaklaşımdır. Başka bir kullanıcı arabirimi kullanan veya Kullanıcı arabirimi olmayan uygulamalar hakkında daha fazla bilgi için bkz. [MFC: belgeler ve görünümler Ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md) ve [MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md). Veritabanı kayıtlarını görüntülemeye yönelik alternatif yaklaşımlar için bkz. Classes [Clienstview](../mfc/reference/clistview-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)
