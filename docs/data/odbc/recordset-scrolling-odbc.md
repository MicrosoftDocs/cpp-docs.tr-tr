---
title: 'Kayıt kümesi: Kaydırma (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5df8151664bd7e726087cb5323c1e4622264ad23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397730"
---
# <a name="recordset-scrolling-odbc"></a>Kayıt kümesi: Kaydırma (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Kayıt açtıktan sonra değerleri görüntülemek için kayıtları erişmek için hesaplamalar yapmak, raporları oluşturma ve benzeri. Kaydırma. kayıt başka bir kayıt kayıt gitmenizi sağlar.

Bu konu şunları açıklar:

- [Bir kayıt kümesinde bir kayıttan kaydırmak nasıl](#_core_scrolling_from_one_record_to_another).

- [Hangi kaydırma durumlarda olan ve desteklenmeyen altında](#_core_when_scrolling_is_supported).

##  <a name="_core_scrolling_from_one_record_to_another"></a> Başka bir kayıttan kaydırma

Sınıf `CRecordset` sağlar `Move` üye işlevleri için bir kayıt kümesi içinde kaydırma. Bu işlevler, satır kümeleri tarafından geçerli kayıt taşıyın. Toplu satır getirme, uyguladıysanız bir `Move` işlemi kayıt kümesi boyutuyla yeniden konumlandırır. Toplu satır getirme, bir çağrı uyguladıysanız değil, bir `Move` işlevi yeniden konumlandırır kayıt kümesi tek bir kayıt olarak her zaman. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
>  Bir kayıt kümesi taşırken, silinen kayıtlar atlandı değildir. Daha fazla bilgi için [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevi.

Ek olarak `Move` İşlevler, `CRecordset` sonundan veya kayıt başından kaydırılan olup olmadığını denetlemek için işlevleri sağlar.

Kaydırmanın kümenize mümkün olup olmadığını belirlemek için çağrı `CanScroll` üye işlevi.

#### <a name="to-scroll"></a>Kaydırmak için

1. Bir kayıt veya bir satır İleri: çağrı [MoveNext](../../mfc/reference/crecordset-class.md#movenext) üye işlevi.

1. Geriye dönük bir kayıt veya bir satır kümesi: çağrı [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) üye işlevi.

1. İlk kayıt kümesinde: çağrı [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) üye işlevi.

1. Son kayıt kümesinde veya son satır kümesi: çağrı [MoveLast](../../mfc/reference/crecordset-class.md#movelast) üye işlevi.

1. *N* geçerli konumuna göre kayıtlar: çağrı [taşıma](../../mfc/reference/crecordset-class.md#move) üye işlevi.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Son veya başlangıç kümesi için test etmek için

1. Son kaydı kaydırma yaptınız? Çağrı [IsEOF](../../mfc/reference/crecordset-class.md#iseof) üye işlevi.

1. (Geriye taşıma) ilk kaydı önceden kaydırma yaptınız? Çağrı [IsBOF](../../mfc/reference/crecordset-class.md#isbof) üye işlevi.

Aşağıdaki kod örneğinde `IsBOF` ve `IsEOF` kaydırma herhangi bir yönde bir kayıt kümesinin sınırlarını algılamak için.

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

`IsEOF` kayıt kümesi son kaydı konumlandırılmış olursa sıfır olmayan bir değer döndürür. `IsBOF` kayıt kümesi (önce tüm kayıtlar) ilk kaydı önüne yerleştirilmiş sıfır olmayan bir değer döndürür. Her iki durumda da, üzerinde çalışılacak geçerli kayıt yok. Çağırırsanız `MovePrev` olduğunda `IsBOF` zaten TRUE veya çağrı `MoveNext` olduğunda `IsEOF` zaten framework oluşturur TRUE ise bir `CDBException`. Ayrıca `IsBOF` ve `IsEOF` boş bir kayıt kümesi için denetlenecek.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. [kayıt kümesi: Yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="_core_when_scrolling_is_supported"></a> Kaydırma Desteklendiğinde

İlk olarak tasarlanan haliyle sadece ileri kaydırma SQL sağlanan ancak ODBC kaydırma yeteneklerini genişletir. Uygulamanızın çalışma sürücünüzün ODBC API uyumluluk düzeyi, ODBC sürücüleri kullanılabilir kaydırma için destek düzeyini bağlıdır ve ODBC imleç kitaplığı belleğe mi yüklenir. Daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!TIP]
>  İmleç Kitaplığı kullanılıp kullanılmadığını kontrol edebilirsiniz. Bkz: *bUseCursorLib* ve *dwOptions* parametreleri [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open).

> [!NOTE]
>  MFC DAO sınıflarına, bir dizi MFC ODBC sınıfları sağlamaz `Find` belirlenmiş ölçütleri karşılayan sonraki (veya önceki) bir kaydı bulmak için çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Kayıt kümesi: Kayıtları Filtreleme (OBDC)](../../data/odbc/recordset-filtering-records-odbc.md)