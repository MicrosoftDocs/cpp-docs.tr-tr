---
description: 'Kayıt kümesi: kaydırma (ODBC) hakkında daha fazla bilgi'
title: 'Kayıt kümesi: Kaydırma (ODBS)'
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
ms.openlocfilehash: 82a4326f2e0a7546d956181e7660ea0f1a437dc6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204465"
---
# <a name="recordset-scrolling-odbc"></a>Kayıt kümesi: Kaydırma (ODBS)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesini açtıktan sonra, değerleri göstermek, hesaplamalar yapmak, raporlar oluşturmak vb. için kayıtlara erişmeniz gerekir. Kaydırma, kayıt kümenizin içinde kayıttan kayda geçiş yapmanızı sağlar.

Bu konuda aşağıdakiler açıklanmaktadır:

- Kayıt [kümesinde bir kayıttan diğerine kaydırma](#_core_scrolling_from_one_record_to_another).

- [Kaydırma hangi koşullarda desteklenir ve desteklenmez](#_core_when_scrolling_is_supported).

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a> Bir kayıttan diğerine kaydırma

Sınıf `CRecordset` , `Move` bir kayıt kümesi içinde kaydırma için üye işlevlerini sağlar. Bu işlevler, geçerli kaydı satır kümelerine göre taşır. Toplu satır getirmeyi uyguladıysanız bir `Move` işlem, kayıt kümesini satır kümesinin boyutuna göre konumlandırır. Toplu satır getirmeyi gerçekleştirdiyseniz, bir işleve yapılan çağrı `Move` , her seferinde kayıt kümesini bir kayıt ile konumlandırır. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> Bir kayıt kümesinden geçiş yaparken, silinen kayıtlar atlanmayabilir. Daha fazla bilgi için [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevine bakın.

İşlevlere ek olarak `Move` , `CRecordset` kayıt kümenizin başlangıcının sonunu mi yoksa önüne mi kayıp kaydırmadığını denetlemek için üye işlevleri sağlar.

Kayıt kümenizde kaydırmanın mümkün olup olmadığını anlamak için `CanScroll` üye işlevini çağırın.

#### <a name="to-scroll"></a>Kaydırmak için

1. Bir kayıt veya bir satır kümesi ilet: [MoveNext](../../mfc/reference/crecordset-class.md#movenext) üye işlevini çağırın.

1. Geriye doğru bir kayıt veya bir satır kümesi: [Moveönceki](../../mfc/reference/crecordset-class.md#moveprev) üye işlevini çağırın.

1. Kayıt kümesindeki ilk kayda: [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) member işlevini çağırın.

1. Kayıt kümesindeki son kayıt veya son satır kümesi: [MoveLast](../../mfc/reference/crecordset-class.md#movelast) üye işlevini çağırın.

1. Geçerli konuma göre *N* kayıt: [Move](../../mfc/reference/crecordset-class.md#move) member işlevini çağırın.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Kayıt kümesinin sonunu veya başlangıcını test etmek için

1. Son kaydı yukarı kaydırdınız mı? IOF [](../../mfc/reference/crecordset-class.md#iseof) üye işlevini çağırın.

1. İlk kaydın önüne kaydırıyorsunuz (geriye doğru hareket)? [IsBOF](../../mfc/reference/crecordset-class.md#isbof) üye işlevini çağırın.

Aşağıdaki kod örneği, `IsBOF` `IsEOF` her iki yönde kaydırılırken bir kayıt kümesinin sınırlarını algılamak için ve kullanır.

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

`IsEOF` kayıt kümesi son kayıttan yerleştirilse sıfır olmayan bir değer döndürür. `IsBOF` kayıt kümesi ilk kaydın önüne konumlandırılmışsa (tüm kayıtlardan önce) sıfır dışında bir değer döndürür. Her iki durumda da, üzerinde çalışılacak geçerli bir kayıt yoktur. Eğer zaten doğru `MovePrev` olduğunda `IsBOF` veya `MoveNext` `IsEOF` ' ı çağırdığınızda, çerçeve bir oluşturur `CDBException` . Ayrıca, `IsBOF` `IsEOF` boş bir kayıt kümesini denetlemek için ve kullanabilirsiniz.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a> Kaydırma destekleniyor

Başlangıçta tasarlanan SQL, yalnızca ileri kaydırma için sağlanmış ancak ODBC, kaydırma yeteneklerini genişletiyor. Kaydırma desteğinin kullanılabilir düzeyi, uygulamanızın birlikte çalışması için, sürücünüzün ODBC API 'SI uyumluluk düzeyi ve ODBC Imleç kitaplığı 'nın belleğe yüklenip yüklenmediğine göre değişir. Daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC: ODBC imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!TIP]
> İmleç kitaplığının kullanılıp kullanılmadığını kontrol edebilirsiniz. [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open)Için *bUseCursorLib* ve *dwOptions* parametrelerine bakın.

> [!NOTE]
> MFC DAO sınıflarının aksine, MFC ODBC sınıfları, `Find` belirtilen ölçütlere uyan bir sonraki (veya önceki) kaydı bulmak için bir işlevler kümesi sağlamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset:: CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset:: CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
