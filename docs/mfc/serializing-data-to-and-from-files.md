---
title: "Veri dosyalarından seri hale getirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d28b12e19b302f5576d2cd76c931e0036c208185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="serializing-data-to-and-from-files"></a>Dosyalarda Verileri Seri Hale Getirme
Kalıcılık temel fikri bir nesneyi kalıcı depolama birimine kendi üye değişkenlerine tarafından gösterilen geçerli durumuna yazabilmesi olacağını değildir. Daha sonra nesneyi okuma ya da "seri durumdan çıkarılırken," nesnenin durumu kalıcı depolama biriminden yeniden oluşturulabilir. Bir anahtar burada nesnenin okuma ve yazma kendi durumuna sorumlu olduğunu noktasıdır. Bu nedenle, kalıcı olması için bir sınıf için temel seri hale getirme işlemlerinin uygulamalıdır.  
  
 Disk dosyalarına yanıt kaydetme olarak belgeleri kaydetmek için bir varsayılan uygulama çerçevesi sağlar ve Dosya menüsünde ve açık komutuna yanıt olarak disk dosyalarından belge yükleme için Kaydet komutları. Çok az çalışmak için ve bir dosyadan verileri okuyup yazmak için bir belgenin özelliği uygulayabilirsiniz. Geçersiz kılma yapmanız gerekir ana şey. [serileştirme](../mfc/reference/cobject-class.md#serialize) belge sınıfınızda üye işlevi.  
  
 MFC Uygulama Sihirbazı'nı iskelet bir geçersiz kılma yerleştirir **CDocument** üye işlevi `Serialize` sizin için oluşturduğu belge sınıfında. Uygulamanızın üye değişkenleri uyguladıktan sonra doldurabilirsiniz, `Serialize` "bir arşiv nesne bir dosyaya bağlı" veri gönderdiğini kodu geçersiz. A [CArchive](../mfc/reference/carchive-class.md) nesne benzer `cin` ve `cout` giriş/çıkış C++ iostream Kitaplığı nesneleri. Ancak, `CArchive` yazar ve ikili biçimi, biçimlendirilmemiş metin okur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Serileştirme](../mfc/serialization-in-mfc.md)  
  
-   [Belgenin rolünde seri hale getirme](#_core_the_document.92.s_role_in_serialization)  
  
-   [Seri hale getirme verilerinin rolü](#_core_the_data.92.s_role_in_serialization)  
  
-   [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a>Belgenin rolünde seri hale getirme  
 Otomatik olarak yanıt verir ve Dosya menüsünde açık olarak framework kaydedin ve belgenin çağırarak komutlar olarak kaydetme `Serialize` onu uygulanmışsa üye işlevi. Bir `ID_FILE_OPEN` komutu, örneğin, application nesnesinde bir işleyici işlevi çağırır. Bu işlem sırasında kullanıcı görür ve Dosya Aç iletişim kutusu yanıt verir ve kullanıcının seçtiği filename framework alır. Framework oluşturur bir `CArchive` kümesi nesnesi için veri belgeye yükleme ve arşive geçirir `Serialize`. Framework zaten dosya açtı. Belgenizin kodda `Serialize` üye işlevi aracılığıyla veri nesneleri gerektiği gibi yeniden oluşturuluyor arşiv verileri okur. Seri hale getirme hakkında daha fazla bilgi için bkz: [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a>Seri hale getirme verilerinin rolünde  
 Genel olarak, sınıf türü veri kendisini seri hale getiremiyor olmalıdır. Diğer bir deyişle, arşive nesneyi geçirdiğinizde, nesnenin kendisini arşive yazma ve kendisini arşivden okuma bilmeniz gerekir. MFC sınıfları bu şekilde serileştirilebilir yapmak için destek sağlar. Bir veri türü tanımlamak için bir sınıf tasarım ve bu tür veriler seri hale getirmek istiyorsanız, seri hale getirme için tasarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

