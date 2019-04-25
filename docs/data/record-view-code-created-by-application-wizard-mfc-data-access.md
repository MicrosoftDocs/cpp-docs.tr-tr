---
title: Uygulama Sihirbazı (MFC veri erişimi)'ın oluşturduğu kayıt görünümü kodu
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: e25ca9cad1390dd11ab7328ffefed31badf6fc0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152689"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Uygulama Sihirbazı (MFC veri erişimi)'ın oluşturduğu kayıt görünümü kodu

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) görünüm geçersiz kılmaları `OnInitialUpdate` ve `OnGetRecordset` üye işlevleri. Çerçeve penceresi, belge ve görünüm framework oluşturduktan sonra çağırdığı `OnInitialUpdate` görünümü başlatılamadı. `OnInitialUpdate` bir işaretçi kayıt kümesine belgeden alır. Temel sınıf için bir çağrı [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) işlevi kayıt açar. Bu işlem için aşağıdaki kodda gösterildiği bir `CRecordView`:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

Kayıt kümesi açıldığında kayıt seçer. [CRecordset::Open](../mfc/reference/crecordset-class.md#open) geçerli kayıt ve form denetimi Görünümü'nde ilgili DDX taşır verilerden kümesinin alan veri üyeleri ilk kaydı yapar. RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md). DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). Belge/görünüm oluşturma işlemi hakkında daha fazla bilgi için bkz. [yazma uygulamaları için Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
>  Son kullanıcılarınızı kayıt kümesindeki kayıt görüntüleme denetimlerini Yenile olanağı vermesi gerekir. Bir kullanıcı için geçersiz bir değer, bir denetimin değeri değişirse bu yetenek olmadan kullanıcı kalıcı olarak geçerli kayıt için takılabilir. Denetimleri yenilemek için çağrı `CWnd` üye işlevi [UpdateData](../mfc/reference/cwnd-class.md#updatedata) parametresi yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)