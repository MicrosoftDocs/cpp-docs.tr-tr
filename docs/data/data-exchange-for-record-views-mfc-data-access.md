---
title: Kayıt görünümleri (MFC veri erişimi) için veri değişimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b6b0109baaf17f804a0ea15eff2e9e766196b86
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052823"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi) için veri değişimi

Kullandığınızda [sınıfı Ekle](../mfc/reference/adding-an-mfc-odbc-consumer.md) kayıt görünümünün iletişim şablon kaynağı denetimlerinde kümesinin alanları eşleştirmek için çift yönlü veri değişimi framework yönetir; denetimleri için kayıt ve kayıt kümesine denetimleri. DDX mekanizması kullanarak kendiniz geri ve İleri veri aktarımı için kod yazmanız gerekmez anlamına gelir.

Kayıt görünümleri için DDX çalışır birlikte [RFX](../data/odbc/record-field-exchange-rfx.md) sınıfın kayıt kümeleri için `CRecordset` (ODBC).  RFX veri kaynağının geçerli kayıt ve kayıt kümesi nesnesi alan veri üyeleri arasında verileri taşır. DDX veri alan veri üyeleri ' form denetimlerinde taşır. Bu birleşim, başlangıçta ve kullanıcı kayıttan kayda form denetimlerini doldurur. Bu da güncelleştirilmiş verileri geri kayıt ve ardından veri kaynağını taşıyabilirsiniz.

Aşağıdaki şekil, kayıt görünümleri için DDX RFX arasındaki ilişkiyi gösterir.

![İletişim&#45;veri değişimi ve kayıt&#45;alan exchange](../data/media/vc37xt1.gif "vc37xt1")<br/>
İletişim kutusu veri değişimi ve kayıt alanı değişimi

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)