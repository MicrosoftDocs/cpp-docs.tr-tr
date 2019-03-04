---
title: Giriş-Çıkış işleme için öneriler
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: 760c213c3af7f9c75374f04e3dfc6b9499eade5c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261979"
---
# <a name="recommendations-for-handling-inputoutput"></a>Giriş/Çıkış İşleme için Öneriler

Veya dosya tabanlı g/ç kullanıp nasıl karar ağacı aşağıdaki sorulara yanıt üzerinde bağlıdır:

**Birincil veri uygulamanızdaki bir disk dosyasında yer almıyor**

- Evet, birincil veri disk dosyasında bulunur:

     **Uygulamanın Dosya Aç belleğe dosyanın tamamını okuyun ve diske geri yazma dosya maliyet tasarrufu dosyanın tamamı**

   - Evet: Varsayılan MFC belge durum budur. Kullanım `CDocument` seri hale getirme.

   - Hayır: Genellikle işlem tabanlı dosyanın güncelleştirme durum budur. İşlem başına temelinde dosyasını güncelleştirin ve gerekmeyen `CDocument` seri hale getirme.

- Hayır, birincil veri disk dosyasında bulunan değil:

     **Verileri bir ODBC veri kaynağında yer almıyor**

   - Evet, verileri bir ODBC veri kaynağında yer alıyor:

         Use MFC's database support. The standard MFC implementation for this case includes a `CDatabase` object, as discussed in the article [MFC: Using Database Classes with Documents and Views](../data/mfc-using-database-classes-with-documents-and-views.md). The application might also read and write an auxiliary file — the purpose of the application wizard "both a database view and file support" option. In this case, you'd use serialization for the auxiliary file.

   - Hayır, verileri bir ODBC veri kaynağında bulunan değil.

         Examples of this case: the data resides in a non-ODBC DBMS; the data is read via some other mechanism, such as OLE or DDE.

         In such cases, you won't use serialization, and your application won't have Open and Save menu items. You might still want to use a `CDocument` as a home base, just as an MFC ODBC application uses the document to store `CRecordset` objects. But you won't use the framework's default File Open/Save document serialization.

Dosya menüsünde komutları kaydedip, kaydetme açık desteklemek için Belge Serileştirme framework sağlar. Serileştirme okur ve nesneleri dahil olmak üzere sınıftan türetilen veri Yazar `CObject`, kadar kalıcı depolama alanı, normalde bir disk dosyası. Seri hale getirme gereksinimlerinizi birçoğu derler ve kullanımı kolaydır, ancak birçok veri erişim uygulamada uygun olabilir. Veri erişimi uygulamaları genellikle veri işlem başına temelinde güncelleştirin. Bunlar, işlem yerine okuma ve tüm veri dosyasını tek seferde yazma tarafından etkilenen kayıtları güncelleştirir.

Seri hale getirme hakkında daha fazla bilgi için bkz. [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Serileştirme vs. Veritabanı giriş/çıkışı](../mfc/serialization-serialization-vs-database-input-output.md)
