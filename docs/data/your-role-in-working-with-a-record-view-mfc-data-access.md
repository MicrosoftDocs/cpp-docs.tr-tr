---
title: Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f84c7491524e8acccb0c904ed51a97ce66bb2151
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056054"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>Kayıt görünümü (MFC veri erişimi) ile çalışırken sizin rolünüz

Aşağıdaki tabloda, genellikle kayıt görünümü ile çalışmak için neler gerekir ve framework sizin için ne yaptığını gösterir.

### <a name="working-with-a-record-view-you-and-the-framework"></a>Kayıt görünümü ile çalışırken: siz ve Framework

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

Form tabanlı programlama veritabanı ile çalışmaya yalnızca bir yaklaşımdır. Başka bir kullanıcı arabirimi veya herhangi bir kullanıcı arabirimi kullanarak uygulamaları hakkında daha fazla bilgi için bkz. [MFC: belgeler ve görünümler ile veritabanı sınıflarını kullanarak](../data/mfc-using-database-classes-with-documents-and-views.md) ve [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md). Veritabanı kayıtlarını görüntüleyen alternatif yaklaşım için bkz: sınıfları [CListView](../mfc/reference/clistview-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)