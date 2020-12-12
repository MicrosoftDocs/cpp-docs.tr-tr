---
description: 'Daha fazla bilgi edinin: kayıt görünümleri için veri değişimi (MFC veri erişimi)'
title: Kayıt görünümleri için veri değişimi (MFC veri erişimi)
ms.date: 11/19/2018
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
ms.openlocfilehash: 6ffb82e3fb1e035b1334e15d5b4d1d25634739c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213214"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Kayıt görünümleri için veri değişimi (MFC veri erişimi)

Bir kayıt görünümünün iletişim şablonu kaynağındaki denetimleri bir kayıt kümesine eşlemek için [Sınıf Ekle](../mfc/reference/adding-an-mfc-odbc-consumer.md) ' yi kullandığınızda, çerçeve veri değişimini her iki yönde yönetir: kayıt kümesinden denetimlere ve denetimlerden kayıt kümesine. DDX mekanizmasının kullanılması, verileri geri ve İleri aktarmak için kodu yazmanız gerekmediği anlamına gelir.

Kayıt görünümleri için DDX, sınıf kayıt kümeleri (ODBC) için [RFX](../data/odbc/record-field-exchange-rfx.md) ile birlikte çalışmaktadır `CRecordset` .  RFX verileri veri kaynağının geçerli kaydı ve bir kayıt kümesi nesnesinin alan veri üyeleri arasında taşıır. DDX, verileri alan verileri üyelerinden form içindeki denetimlere taşıdıkça. Bu birleşim, form denetimlerini başlangıçta ve kullanıcı kayıttan kayda taşırken doldurur. Ayrıca, güncelleştirilmiş verileri kayıt kümesine ve ardından veri kaynağına geri taşıyabilir.

Aşağıdaki şekilde, kayıt görünümleri için DDX ve RFX arasındaki ilişki gösterilmektedir.

![İletişim&#45;veri değişimi ve kayıt&#45;alan değişimi](../data/media/vc37xt1.gif "İletişim&#45;veri değişimi ve kayıt&#45;alan değişimi")<br/>
İletişim kutusu veri değişimi ve kayıt alanı değişimi

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). RFX hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)
