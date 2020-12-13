---
description: 'Hakkında daha fazla bilgi edinin: uygulama tarafından oluşturulan kayıt görünümü kodu (MFC veri erişimi)'
title: Uygulama Sihirbazı tarafından oluşturulan kayıt görünümü kodu (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: b0fa7a4960096f11ab66194fa6e41be60b45d4c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332437"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Uygulama Sihirbazı tarafından oluşturulan kayıt görünümü kodu (MFC veri erişimi)

[MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md) , görünümün `OnInitialUpdate` ve `OnGetRecordset` üye işlevlerini geçersiz kılar. Çerçeve penceresini, belgeyi ve görünümünü oluşturduktan sonra, `OnInitialUpdate` görünümü başlatmak için çağırır. `OnInitialUpdate` belgeden kayıt kümesine bir işaretçi alır. Temel sınıf [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) işlevine yapılan bir çağrı, kayıt kümesini açar. Aşağıdaki kod, için bu işlemi gösterir `CRecordView` :

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

Kayıt kümesi açıldığında kayıtları seçer. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) , ilk kaydı geçerli kayıt yapar ve DDX kayıt kümesinin alan verileri üyelerinden verileri görünümdeki ilgili form denetimlerine taşıır. RFX hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md). DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). Belge/görünüm oluşturma işlemi hakkında daha fazla bilgi için bkz. [Windows Için uygulama yazmak Için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
> Son kullanıcılarınıza kayıt kümesi denetimlerini kayıt kümesinden yenileme özelliği sağlamanız gerekir. Bu özellik olmadan, bir Kullanıcı bir denetimin değerini geçersiz bir değere değiştirirse, Kullanıcı kalıcı olarak geçerli kayıt üzerinde kalmış olabilir. Denetimleri yenilemek için, `CWnd` [UpdateData](../mfc/reference/cwnd-class.md#updatedata) üye işlevini yanlış parametresiyle çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)
