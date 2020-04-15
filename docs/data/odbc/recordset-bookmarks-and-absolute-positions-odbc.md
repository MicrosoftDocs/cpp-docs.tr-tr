---
title: 'Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)'
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: 77c8bbaf7c0bc21dab62c3785364e72656287815
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367061"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt setinde gezinirken, genellikle belirli bir kayda geri dönmenin bir yolunu bulmanız gerekir. Bir kaydın yer imi ve mutlak konumu bu tür iki yöntem sağlar.

Bu konu açıklar:

- [Yer imleri nasıl kullanılır.](#_core_bookmarks_in_mfc_odbc)

- [Mutlak pozisyonları kullanarak geçerli kayıt nasıl ayarlanan.](#_core_absolute_positions_in_mfc_odbc)

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a>MFC ODBC'de yer imleri

Yer imi bir kaydı benzersiz olarak tanımlar. Bir kayıt kümesinde gezinirken, kayıtlar kayıt kümesinden silinebileceğinden, her zaman bir kaydın mutlak konumuna güvenemezsiniz. Bir kaydın konumunu izlemenin güvenilir yolu yer imi kullanmaktır. Sınıf `CRecordset` malzemeleri üye işlevleri için:

- Geçerli kaydın yer işaretini alma, böylece bir değişken[(GetBookmark)](../../mfc/reference/crecordset-class.md#getbookmark)kaydedebilirsiniz.

- Daha önce bir değişkene kaydettiğiniz yer işaretini belirterek belirli bir kayda hızlı bir şekilde geçme[(SetBookmark).](../../mfc/reference/crecordset-class.md#setbookmark)

Aşağıdaki örnekte, geçerli kaydı işaretlemek ve daha sonra ona dönmek için bu üye işlevlerin nasıl kullanılacağı gösteriş verilmiştir:

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

[CDBVariant Class](../../mfc/reference/cdbvariant-class.md) nesnesinden temel veri türünü ayıklamanız gerekmez. Değeri ile `GetBookmark` atayın ve yer işaretine '' ile `SetBookmark`geri dönün.

> [!NOTE]
> ODBC sürücünüze ve kayıt kümesi türünüze bağlı olarak yer imleri desteklenmeyebilir. Yer imlerinin [CRecordset::CanBookmark'ı](../../mfc/reference/crecordset-class.md#canbookmark)arayarak desteklenip desteklenmediğini kolayca belirleyebilirsiniz. Ayrıca, yer imleri desteklenirse, [CRecordset:Open](../../mfc/reference/crecordset-class.md#open) üye `CRecordset::useBookmarks` işlevinde seçeneği belirterek bunları uygulamayı açıkça seçmelisiniz. Ayrıca, belirli kayıt kümesi işlemlerinden sonra yer imlerinin kalıcılığını da kontrol etmelisiniz. Örneğin, bir `Requery` kayıt kümesiyseniz, yer imleri artık geçerli olmayabilir. CDatabase'i arayın::Güvenli bir şekilde arayıp arayamayacağınızı kontrol etmek için [GetBookmarkPersistence'](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) ı arayın. `SetBookmark`

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a>MFC ODBC'de Mutlak Pozisyonlar

Yer imleri `CRecordset` dışında, sınıf bir ordinal pozisyon belirterek geçerli kaydı ayarlamak için izin verir. Buna mutlak konumlandırma denir.

> [!NOTE]
> Yalnızca ileri kayıt kümelerinde mutlak konumlandırma kullanılamaz. Yalnızca ileri kayıt kümeleri hakkında daha fazla bilgi için [Bkz. Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md).

Geçerli kayıt işaretçisini mutlak konumu kullanarak taşımak için [CRecordset'i arayın::SetAbsolutePosition.](../../mfc/reference/crecordset-class.md#setabsoluteposition) Bir değeri `SetAbsolutePosition`geçtiğizde, bu ordinal konuma karşılık gelen kayıt geçerli kayıt olur.

> [!NOTE]
> Bir kaydın mutlak konumu potansiyel olarak güvenilmezdir. Kullanıcı kayıtları kayıt kümesinden silerse, sonraki kayıtların ordinal konumu değişir. Yer imleri, geçerli kaydı taşımak için önerilen yöntemdir. Daha fazla bilgi için [MFC ODBC'deki Yer İşaretleri'ne](#_core_bookmarks_in_mfc_odbc)bakın.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için Bkz. [Kayıt Kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)
