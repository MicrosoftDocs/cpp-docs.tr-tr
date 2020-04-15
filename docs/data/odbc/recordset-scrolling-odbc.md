---
title: 'Kayıt Kümesi: Kaydırma (ODBC)'
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
ms.openlocfilehash: 931051296dff495939fcbd894102a1b00e48ee90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366934"
---
# <a name="recordset-scrolling-odbc"></a>Kayıt Kümesi: Kaydırma (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesini açtıktan sonra, değerleri görüntülemek, hesaplamalar yapmak, raporlar oluşturmak ve benzeri kayıtlara erişmeniz gerekir. Kaydırma, kayıt setinizin içinde kayıttan kayda geçmenizi sağlar.

Bu konu açıklar:

- [Kayıt kümesinde bir kayıttan diğerine kaydırma nasıl.](#_core_scrolling_from_one_record_to_another)

- Kaydırma hangi koşullar altında ve [desteklenmez.](#_core_when_scrolling_is_supported)

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a>Bir Kayıttan Diğerine Kaydırma

Sınıf, `CRecordset` `Move` kayıt kümesi içinde kaydırma için üye işlevleri sağlar. Bu işlevler geçerli kaydı satır kümeleri tarafından taşır. Toplu satır alma işlemini uyguladıysanız, bir `Move` işlem kayıt kümesini rowset boyutuna göre yeniden konumlandırIr. Toplu satır alma uygulamadıysanız, bir `Move` işlev çağrısı her seferinde bir kayıt tarafından kayıt kümesini yeniden konumlandırIr. Toplu satır alma hakkında daha fazla bilgi için bkz: [Recordset: Toplu Olarak Kayıtları Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> Kayıt kümesinde hareket ederken, silinen kayıtlar atlanamayabilir. Daha fazla bilgi [için, Silinmiş](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevine bakın.

`Move` Fonksiyonlara ek olarak, `CRecordset` kayıt setinizin başında veya sonundan önce kaydırDığınızı denetlemek için üye işlevler sağlar.

Kayıt setinizde kaydırmanın mümkün olup olmadığını `CanScroll` belirlemek için üye işlevini arayın.

#### <a name="to-scroll"></a>Kaydırma kin

1. Bir kaydı veya bir rowset'i ileri: [MoveNext](../../mfc/reference/crecordset-class.md#movenext) üye işlevini arayın.

1. Geriye doğru bir kayıt veya bir rowset: [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) üye işlevini arayın.

1. Kayıt kümesindeki ilk kayda: [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) üye işlevini arayın.

1. Kayıt kümesindeki son kayda veya son satır kümesine: [MoveLast](../../mfc/reference/crecordset-class.md#movelast) üye işlevini arayın.

1. *N,* geçerli konuma göre kayıt: [Taşı](../../mfc/reference/crecordset-class.md#move) üye işlevini çağırın.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Kayıt kümesinin sonu veya başlangıcı için test etmek için

1. Son kaydı geçtin mi? [IsEOF](../../mfc/reference/crecordset-class.md#iseof) üye işlevini arayın.

1. İlk kaydın önüne geçtiniz mi (geriye doğru hareket ediyor)? [IsBOF](../../mfc/reference/crecordset-class.md#isbof) üye işlevini arayın.

Aşağıdaki kod örneği `IsBOF` `IsEOF` kullanır ve her iki yönde kaydırma yaparken bir kayıt kümesinin sınırlarını algılamak için.

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

`IsEOF`kayıt kümesi son kaydın ötesine konumlandırılmışsa sıfır olmayan bir değer döndürür. `IsBOF`kayıt kümesi ilk kaydın önüne yerleştirilmişse (tüm kayıtlardan önce) sıfır olmayan bir değer döndürür. Her iki durumda da, çalışacak geçerli bir kayıt yoktur. Zaten DOĞRU `MovePrev` `IsBOF` olduğunda veya zaten `MoveNext` `IsEOF` DOĞRU olduğunda arama, çerçeve `CDBException`atar . Boş bir `IsBOF` kayıt `IsEOF` kümesini de kullanabilir ve kontrol edebilirsiniz.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)adlı telefon adedine bakın.

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a>Kaydırma Desteklendiğinde

Başlangıçta tasarlandığı gibi, SQL yalnızca ileri kaydırma sağladı, ancak ODBC kaydırma yeteneklerini genişletiyor. Kaydırma için kullanılabilir destek düzeyi, uygulamanızın birlikte çalıştığı ODBC sürücülerine, sürücünüzün ODBC API uyumluluk düzeyine ve ODBC İmleç Kitaplığı'nın belleğe yüklenip yüklenmediğine bağlıdır. Daha fazla bilgi için [Bkz. ODBC](../../data/odbc/odbc-basics.md) ve [ODBC: ODBC İmleç Kitaplığı.](../../data/odbc/odbc-the-odbc-cursor-library.md)

> [!TIP]
> İmleç kitaplığı kullanılıp kullanılmadığını denetleyebilirsiniz. Bkz. *bUseCursorLib* ve *dwOptions* parametreleri [CDatabase için::Aç](../../mfc/reference/cdatabase-class.md#open).

> [!NOTE]
> MFC DAO sınıflarının aksine, MFC ODBC sınıfları `Find` belirtilen ölçütleri karşılayan sonraki (veya önceki) kaydı bulmak için bir dizi işlev sağlamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetHatası](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
