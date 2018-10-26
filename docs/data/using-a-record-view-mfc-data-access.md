---
title: Kayıt görünümü (MFC veri erişimi) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3af338f4c88b2fa7268387ef0701f52a813b0d49
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056210"
---
# <a name="using-a-record-view--mfc-data-access"></a>(MFC veri erişimi) kayıt görünümünü kullanma

Bu konu, sihirbaz sizin yerinize yazar kayıt görünümleri için varsayılan kod yaygın olarak nasıl özelleştirebileceğinizi açıklar. Kayıt seçimi kısıtlamak istediğiniz genellikle bir [filtre](../data/odbc/recordset-filtering-records-odbc.md) veya [parametreleri](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), belki de [sıralama](../data/odbc/recordset-sorting-records-odbc.md) kayıtlar, SQL deyimini özelleştirme.

Kullanarak `CRecordView` çok aynı kullanarak [CFormView](../mfc/reference/cformview-class.md). Temel yaklaşım görüntülemek ve belki de tek bir kayıt kümesinin kayıtları güncelleştirmek için kayıt görünümü kullanmaktır. Bundan sonraki miktarlar diğer kayıt kümeleri de açıklandığı gibi kullanmak isteyebilirsiniz [kayıt görünümleri: ikinci kayıt kümesinden liste kutusunu doldurma](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)