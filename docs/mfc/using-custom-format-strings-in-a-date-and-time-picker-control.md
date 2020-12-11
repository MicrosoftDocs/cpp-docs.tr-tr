---
description: 'Hakkında daha fazla bilgi edinin: Tarih ve saat seçici denetiminde özel biçim dizeleri kullanma'
title: Tarih ve Saat Seçici Denetiminde Özel Biçim Dizeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 91add199ffd852a107588617d47a2fd51136596d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154558"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetiminde Özel Biçim Dizeleri Kullanma

Varsayılan olarak, tarih ve saat seçici denetimleri, geçerli tarih veya saati görüntülemek için üç biçim türü (benzersiz bir stile karşılık gelen her biçim) sağlar:

- **dts_longdateformat** Tarihi uzun biçimde görüntüler, "Çarşamba, Ocak 3, 2000" gibi bir çıktı üretir.

- **dts_shortdateformat** Tarihi, "1/3/00" gibi bir çıktı üreten kısa biçimde görüntüler.

- **DTS_TIMEFORMAT** "5:31:42 PM" gibi çıktıyı üreten süreyi uzun biçimde görüntüler.

Ancak, bir özel biçim dizesi kullanarak tarih veya saatin görünümünü özelleştirebilirsiniz. Bu özel dize, varolan biçim karakterlerinden, biçim olmayan karakterlerden veya her ikisinin birleşimini oluşur. Özel dize derlendikten sonra, özel dizeniz içinde [CDateTimeCtrl:: SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) geçişine yönelik bir çağrı yapın. Tarih ve saat seçici denetimi, geçerli değeri özel biçim dizenizi kullanarak görüntüler.

Aşağıdaki örnek kod ( *m_dtPicker* `CDateTimeCtrl` nesne) olası bir çözümü gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

Özel biçim dizelerine ek olarak tarih ve saat seçici denetimleri de [geri arama alanlarını](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)destekler.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
