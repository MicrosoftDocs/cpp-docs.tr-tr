---
title: Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
ms.openlocfilehash: c5c35208f654cff90e3cdf87e697e654bdfbe307
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033011"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz

Aşağıdaki tabloda, genellikle kayıt görünümü ile çalışmak için neler gerekir ve framework sizin için ne yaptığını gösterir.

### <a name="working-with-a-record-view-you-and-the-framework"></a>Kayıt görünümü ile çalışırken: Siz ve Framework

|Bunun için,|Framework|
|---------|-------------------|
|Formu tasarlamak için Visual C++ iletişim kutusu düzenleyicisini kullanın.|Bir iletişim şablonunu kaynağı denetimleriyle oluşturur.|
|Kullanım [MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) öğelerinden türetilen sınıfları oluşturmak için [CRecordView](../mfc/reference/crecordview-class.md) ve [CRecordset](../mfc/reference/crecordset-class.md).|Sınıflar, sizin yerinize yazar.|
|Kayıt görünümü denetimleri için kayıt kümesi alan veri üyeleri eşleyin.|DDX denetimleri ve kayıt alanları arasında sağlar.|
||Varsayılan için komut işleyicileri sağlar **taşıma ilk**, **sona Taşı**, **sonrakine Taşı**, ve **öncekine taşı** menü veya araç komutları düğmeler.|
||Değişiklikleri veri kaynağına güncelleştirir.|
|[İsteğe bağlı] Liste kutuları veya birleşik giriş kutuları veya diğer denetimleri, ikinci kayıt kümesinden verilerle doldurmak için kod yazın.||
|[İsteğe bağlı] Herhangi bir özel doğrulama için kod yazın.||
|[İsteğe bağlı] Kayıtlarını eklemek veya silmek için kod yazın.||

Form tabanlı programlama veritabanı ile çalışmaya yalnızca bir yaklaşımdır. Başka bir kullanıcı arabirimi veya herhangi bir kullanıcı arabirimi kullanarak uygulamaları hakkında daha fazla bilgi için bkz. [MFC: Belgeler ve görünümler ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md) ve [MFC: Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md). Veritabanı kayıtlarını görüntüleyen alternatif yaklaşım için bkz: sınıfları [CListView](../mfc/reference/clistview-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)