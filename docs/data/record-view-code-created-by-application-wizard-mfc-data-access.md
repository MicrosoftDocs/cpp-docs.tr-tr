---
title: Kayıt görünümü kodu (MFC veri erişimi) uygulama Sihirbazı tarafından oluşturulan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15355d156b3c85c8f99ba638b30f831da96686af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Uygulama Sihirbazı (MFC veri erişimi)'ın oluşturduğu kayıt görünümü kodu
[MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md) görünümün geçersiz kılmaları `OnInitialUpdate` ve `OnGetRecordset` üye işlevleri. Çerçeve penceresi, belge ve görünüm framework oluşturduktan sonra çağırır `OnInitialUpdate` görünümü başlatılamadı. `OnInitialUpdate` bir işaretçi kayıt kümesine belgeden alır. Taban sınıfı için bir çağrı [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) işlevi kayıt kümesi açar. Bu işlem için aşağıdaki kodu gösterir bir `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 Kayıt kümesi açıldığında kayıtları seçer. [CRecordset::Open](../mfc/reference/crecordset-class.md#open) geçerli kayıt ve denetimleri form görünümü içinde karşılık gelen DDX taşır verilerden kayıt kümesinin alan veri üyeleri ilk kaydı yapar. RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md). DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). Belge/görünüm oluşturma işlemi hakkında daha fazla bilgi için bkz: [yazma uygulamaları Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Son kullanıcılarınıza kayıt kümesindeki kayıt görünümü denetimleri yenileme olanağı vermesi gerekir. Bir kullanıcı için geçersiz bir değer, bir denetimin değeri değişirse bu yetenek olmadan kullanıcının kalıcı olarak geçerli kayıtta takılabilir. Denetimleri yenilemek için arama `CWnd` üye işlevi [UpdateData](../mfc/reference/cwnd-class.md#updatedata) bir parametresi ile **FALSE**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)