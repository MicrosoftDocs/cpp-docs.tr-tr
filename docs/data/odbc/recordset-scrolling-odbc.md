---
title: "Kayıt kümesi: Kaydırma (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34dcfb9cb1d45710accba2ee6155e3c741b727be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-scrolling-odbc"></a>Kayıt Kümesi: Kaydırma (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bir kayıt kümesini açtıktan sonra değerleri görüntülemek için kayıtları erişmek için hesaplamalar yapmak, raporları oluşturmak ve benzeri. Kaydırma kümenizin içinde kayıttan kayda gitmenizi sağlar.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Bir kayıt kümesinde bir kayıttan kaydırmak nasıl](#_core_scrolling_from_one_record_to_another).  
  
-   [Ne kaydırma durumlarda olan ve desteklenmeyen altında](#_core_when_scrolling_is_supported).  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a>Bir kayıttan diğerine kaydırma  
 Sınıf `CRecordset` sağlar **taşıma** kayıt kümesi içinde kaydırma için üye işlevleri. Bu işlevler geçerli kaydı satır kümelerine göre taşır. Toplu satır getirme, uyguladıysanız bir **taşıma** işlemi kayıt kümesi satır kümesi boyutu tarafından yeniden konumlandırır. Toplu satır getirme, çağrı uyguladıysanız olmayan bir **taşıma** işlevi yeniden konumlandırır kayıt kümesi tek bir kayıt olarak her zaman. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Bir kayıt kümesinin üstünden geçerken silinmiş kayıtlar atlandı değildir. Daha fazla bilgi için bkz: [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevi.  
  
 Ek olarak **taşıma** İşlevler, `CRecordset` sonundan sonraya veya kümenizin başından kaydırılan olup olmadığını denetlemek için üye işlevleri sağlar.  
  
 Kaydırma kümenize mümkün olup olmadığını belirlemek için çağrı `CanScroll` üye işlevi.  
  
#### <a name="to-scroll"></a>Kaydırma  
  
1.  Bir kayıt veya bir satır kümesi iletin: çağrı [MoveNext](../../mfc/reference/crecordset-class.md#movenext) üye işlevi.  
  
2.  Geriye dönük bir kayıt veya bir satır kümesi: çağrı [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) üye işlevi.  
  
3.  Kayıt kümesindeki ilk kaydı için: çağrı [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) üye işlevi.  
  
4.  Kayıt kümesindeki son kayıt veya son satır: çağrı [MoveLast](../../mfc/reference/crecordset-class.md#movelast) üye işlevi.  
  
5.  *N* geçerli konumu göre kaydeder: çağrı [taşıma](../../mfc/reference/crecordset-class.md#move) üye işlevi.  
  
#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Son veya kayıt başlangıcı için test etme  
  
1.  Son kaydı kaydırılan mi? Çağrı [IsEOF](../../mfc/reference/crecordset-class.md#iseof) üye işlevi.  
  
2.  (Geriye taşıma) ilk kayıt öncesine kaydırma yaptınız? Çağrı [IsBOF](../../mfc/reference/crecordset-class.md#isbof) üye işlevi.  
  
 Aşağıdaki kod örneğinde `IsBOF` ve `IsEOF` herhangi bir yönde kaydırma bir kayıt kümesinin sınırlarını algılamak için.  
  
```  
// Open a recordset; first record is current  
CCustSet rsCustSet( NULL );  
rsCustSet.Open( );  
  
if( rsCustSet.IsBOF( ) )  
    return;  
    // The recordset is empty  
  
// Scroll to the end of the recordset, past  
// the last record, so no record is current  
while ( !rsCustSet.IsEOF( ) )  
    rsCustSet.MoveNext( );  
  
// Move to the last record  
rsCustSet.MoveLast( );  
  
// Scroll to beginning of the recordset, before  
// the first record, so no record is current  
while( !rsCustSet.IsBOF( ) )  
    rsCustSet.MovePrev( );  
  
// First record is current again  
rsCustSet.MoveFirst( );  
```  
  
 `IsEOF`kayıt kümesi son kaydı konumlandırılır, sıfır olmayan bir değer döndürür. `IsBOF`kayıt kümesi (önce tüm kayıtları) ilk kaydı öncesinde konumlandırılır, sıfır olmayan bir değer döndürür. Her iki durumda da, üzerinde çalışılacak geçerli kayıt yok. Çağırırsanız `MovePrev` zaman `IsBOF` zaten **TRUE** veya arama `MoveNext` zaman `IsEOF` zaten **TRUE**, framework oluşturur bir `CDBException`. Aynı zamanda `IsBOF` ve `IsEOF` için boş bir kayıt kümesi denetlemek için.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için bkz: [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="_core_when_scrolling_is_supported"></a>Kaydırma Desteklendiğinde  
 İlk olarak tasarlanan haliyle yalnızca ileri kaydırma SQL sağlanan ancak ODBC kaydırma yeteneklerini genişletir. Uygulamanızı çalışır sürücünüzün ODBC API uyumluluk düzeyi, ODBC sürücüleri kaydırma desteği kullanılabilir düzeyine bağlıdır ve ODBC imleç kitaplığı belleğe mi yüklenir. Daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!TIP]
>  İmleç Kitaplığı kullanılıp kullanılmadığını kontrol edebilirsiniz. Bkz: `bUseCursorLib` ve `dwOptions` parametreleri [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open).  
  
> [!NOTE]
>  MFC DAO sınıflarını, bir dizi MFC ODBC sınıfları sağlamaz **Bul** belirtilen ölçütleri karşılayan sonraki (veya önceki) kaydını bulmak için çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)   
 [CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)   
 [Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)