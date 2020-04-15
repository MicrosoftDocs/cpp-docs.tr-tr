---
title: Uygulama Sihirbazı tarafından Oluşturulan Kayıt Görünümü Kodu (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: 69481299980329b98e378f02e090670fa3d7ece2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376028"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Uygulama Sihirbazı tarafından Oluşturulan Kayıt Görünümü Kodu (MFC Data Access)

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) görünümün `OnInitialUpdate` ve `OnGetRecordset` üye işlevlerini geçersiz kılar. Çerçeve çerçeve penceresi, belge ve görünüm oluşturduktan `OnInitialUpdate` sonra, görünümü başlatmayı çağırır. `OnInitialUpdate`belgeden kayıt kümesiiçin bir işaretçi alır. Temel sınıf CView için bir [çağrı::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) işlevi kayıt kümesini açar. Aşağıdaki kod için `CRecordView`bu işlemi gösterir:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

Kayıt kümesi açıldığında, kayıtları seçer. [CRecordset::Open,](../mfc/reference/crecordset-class.md#open) geçerli kaydı ilk kaydeder ve DDX verileri kayıt kümesinin alan veri üyelerinden görünümdeki ilgili form denetimlerine taşır. RFX hakkında daha fazla bilgi için [Kayıt Alanı Değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md)'ye bakın. DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../mfc/dialog-data-exchange-and-validation.md)bakın. Belge/görünüm oluşturma işlemi hakkında bilgi için windows [için uygulama yazmak için Sınıfları Kullanma'ya](../mfc/using-the-classes-to-write-applications-for-windows.md)bakın.

> [!NOTE]
> Son kullanıcılarınıza kayıt kümesinden kayıt görünümü denetimlerini yenileme olanağı vermelisiniz. Bu özellik olmadan, bir kullanıcı denetimin değerini geçersiz bir değerle değiştirirse, kullanıcı geçerli kayda kalıcı olarak takılabilir. Denetimleri yenilemek `CWnd` için, üye işlevi [UpdateData'yı](../mfc/reference/cwnd-class.md#updatedata) FALSE parametresi ile çağırırsınız.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Görünümü Kullanma](../data/using-a-record-view-mfc-data-access.md)
