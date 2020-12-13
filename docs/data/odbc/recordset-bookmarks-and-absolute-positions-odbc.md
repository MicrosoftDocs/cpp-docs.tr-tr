---
description: 'Daha fazla bilgi: kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)'
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
ms.openlocfilehash: b52ca2e43a89a6cab0e9197d8dbf32c321feca5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186122"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir kayıt kümesi içinde gezinilirken, genellikle belirli bir kayda dönme yöntemine ihtiyacınız vardır. Bir kaydın yer işareti ve mutlak konumu iki tür yöntemi sağlar.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Yer imlerini kullanma](#_core_bookmarks_in_mfc_odbc).

- [Mutlak konumları kullanarak geçerli kaydı ayarlama](#_core_absolute_positions_in_mfc_odbc).

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC 'de yer işaretleri

Bir yer işareti, bir kaydı benzersiz şekilde tanımlar. Bir kayıt kümesinden gittiğinizde, kayıtlar kayıt kümesinden silinebildiğinden kaydın mutlak konumuna her zaman güvenebilirsiniz. Bir kaydın konumunu izlemenin güvenilir yolu, onun yer işaretini kullanmaktır. Sınıfı `CRecordset` için üye işlevleri sağlar:

- Geçerli kaydın yer işaretinin alınması, bu sayede bir değişkene ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)) kaydedebilirsiniz.

- Daha önce bir değişkende ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)) kaydettiğiniz yer işaretini belirterek, belirli bir kayda hızlıca geçiş yapın.

Aşağıdaki örnek, geçerli kaydı işaretlemek ve daha sonra buna dönmek için bu üye işlevlerinin nasıl kullanılacağını gösterir:

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

[CDBVariant sınıfı](../../mfc/reference/cdbvariant-class.md) nesnesinden temel alınan veri türünü ayıklamaya gerek yoktur. Değerini ile atayın `GetBookmark` ve ile bu yer işaretine dönün `SetBookmark` .

> [!NOTE]
> ODBC sürücünüze ve kayıt kümesi türüne bağlı olarak, yer işaretleri desteklenmeyebilir. Yalnızca [CRecordset:: CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)çağırarak yer işaretlerinin desteklenip desteklenmediğini kolayca belirleyebilirsiniz. Ayrıca, yer işaretleri destekleniyorsa, `CRecordset::useBookmarks` [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) üye işlevindeki seçeneği belirterek açıkça bunları uygulamayı tercih etmeniz gerekir. Ayrıca, belirli kayıt kümesi işlemlerinden sonra yer işaretlerinin kalıcılığını denetlemeniz gerekir. Örneğin, `Requery` bir kayıt kümeniz varsa, yer işaretleri artık geçerli olmayabilir. Güvenli bir şekilde çağırıp çağıramayacağını denetlemek için [CDatabase:: Getbookmarkkalıcılığı](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) çağırın `SetBookmark` .

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC 'de mutlak Pozisyonlar

Yer işaretlerinin yanı sıra, sınıfı `CRecordset` bir sıra konumu belirterek geçerli kaydı ayarlamanıza olanak sağlar. Bu mutlak konumlandırma olarak adlandırılır.

> [!NOTE]
> Mutlak konumlandırma yalnızca iletme kayıt kümelerinde kullanılamaz. Salt iletme kayıt kümeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).

Mutlak konum kullanarak geçerli kayıt işaretçisini taşımak için [CRecordset:: SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)çağırın. ' A bir değer geçirdiğinizde `SetAbsolutePosition` , bu sıra konumuna karşılık gelen kayıt geçerli kayıt haline gelir.

> [!NOTE]
> Bir kaydın mutlak konumu büyük olasılıkla güvenilmez. Kullanıcı kayıt kümesinden kayıtları silerse, sonraki kaydın sıra konumu değişir. Yer işaretleri, geçerli kaydı taşımak için önerilen yöntemdir. Daha fazla bilgi için bkz. [MFC ODBC 'de yer işaretleri](#_core_bookmarks_in_mfc_odbc).

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)
