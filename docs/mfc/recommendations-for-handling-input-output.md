---
description: 'Daha fazla bilgi: giriş/çıkış Işleme önerileri'
title: Input-Output Işleme için öneriler
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: c9a1acab50dc95f12d3002f54f4ab0819c041068
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248495"
---
# <a name="recommendations-for-handling-inputoutput"></a>Giriş/Çıkış İşleme için Öneriler

Dosya tabanlı g/ç veya kullanma gibi, aşağıdaki karar ağacındaki sorulara nasıl yanıt verdiğinize bağlı değildir:

**Uygulamanızdaki birincil veriler bir disk dosyasında yer alır**

- Evet, birincil veriler bir disk dosyasında bulunur:

   **Uygulama dosya açıkken tüm dosyayı belleğe okur ve dosya kaydetme sırasında tüm dosyayı diske geri yazar**

  - Evet: Bu varsayılan MFC belge durumdur. `CDocument`Serileştirme kullanın.

  - Hayır: Bu genellikle dosyanın işlem tabanlı güncelleştirilmesi durumunda oluşur. Dosyayı işlem başına temelinde güncelleştirmeniz ve `CDocument` Serileştirmeye gerek kalmaz.

- Hayır, birincil veriler disk dosyasında yer almaz:

   **Veriler bir ODBC veri kaynağında bulunur**

  - Evet, veriler ODBC veri kaynağında bulunuyor:

      MFC 'nin veritabanı desteğini kullanın. Bu durum için standart MFC uygulamasında `CDatabase` [MFC: belgeler ve görünümler Ile veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-with-documents-and-views.md)başlıklı makalede açıklandığı gibi bir nesne vardır. Uygulama ayrıca bir yardımcı dosyayı okuyabilir ve yazabilir (uygulama Sihirbazı 'nın her ikisi de bir veritabanı görünümü ve dosya desteği "seçeneğidir). Bu durumda, yardımcı dosya için serileştirme kullanacaksınız.

  - Hayır, veriler ODBC veri kaynağında yer almamalıdır.

      Bu örneğe örnekler: veriler ODBC olmayan bir DBMS 'de bulunur; veriler OLE veya DDE gibi başka bir mekanizma aracılığıyla okunabilir.

      Bu gibi durumlarda serileştirme kullanmayacaktır ve uygulamanız menü öğelerini açıp kaydetmezler. Bir `CDocument` MFC ODBC uygulaması, nesneleri depolamak için belgeyi kullandığından, yine de bir giriş tabanı olarak kullanmak isteyebilirsiniz `CRecordset` . Ancak çerçevenin varsayılan dosyasını aç/kaydet belge serileştirmesini kullanamazsınız.

Dosya menüsünde Aç, Kaydet ve farklı Kaydet komutlarını desteklemek için Framework belge serileştirmesi sağlar. Serileştirme, sınıftan türetilmiş nesneler dahil, `CObject` normal olarak bir disk dosyası olan verileri okur ve yazar. Serileştirme kullanımı kolaydır ve gereksinimlerinize çok sayıda hizmet sunar, ancak birçok veri erişimi uygulamasında uygunsuz olabilir. Veri erişimi uygulamaları, verileri genellikle işlem başına temelinde güncelleştirir. Tüm veri dosyalarını bir kerede okumak ve yazmak yerine işlemin etkilediği kayıtları güncelleştirirler.

Serileştirme hakkında daha fazla bilgi için bkz. [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme: serileştirme ve veritabanı giriş/çıkış karşılaştırması](../mfc/serialization-serialization-vs-database-input-output.md)
