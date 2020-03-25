---
title: Kayıt görünümü kullanma (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: 611ddfd755eec84d4f2572a50c18802f988c5c3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209033"
---
# <a name="using-a-record-view--mfc-data-access"></a>Kayıt görünümü kullanma (MFC veri erişimi)

Bu konuda, sihirbazın sizin için yazdığı kayıt görünümleri için varsayılan kodu yaygın olarak nasıl özelleştirebileceğiniz açıklanmaktadır. Genellikle, kayıt seçimini bir [filtre](../data/odbc/recordset-filtering-records-odbc.md) veya [parametrelerle](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)kısıtlamak, belki de kayıtları [sıralamak](../data/odbc/recordset-sorting-records-odbc.md) , SQL ifadesini özelleştirmek istersiniz.

`CRecordView` kullanmak [CFormView](../mfc/reference/cformview-class.md)kullanarak çok benzer. Temel yaklaşım, tek bir kayıt kümesinin kayıtlarını görüntülemek ve belki güncelleştirmek için kayıt görünümünü kullanmaktır. Bunun ötesinde, diğer kayıt kümelerini de ( [Kayıt görünümleri: bir liste kutusunu ikinci bir kayıt kümesinden doldurma](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)bölümünde açıklandığı gibi) kullanmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)
