---
title: "CArchive nesnesi oluşturmanın iki yolu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CArchive
dev_langs: C++
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b1db549544d421600ed6dae1a8a987006c2ab6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive Nesnesi Oluşturmanın İki Yolu
Oluşturmanın iki yolu vardır bir `CArchive` nesnesi:  
  
-   [CArchive nesnesi çerçevesi aracılığıyla örtük oluşturma](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [CArchive nesnesi açık oluşturma](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>CArchive nesnesi çerçevesi aracılığıyla örtük oluşturma  
 Oluşturduğunuz iskelet izin vermek için en yaygın ve kolay bir yol olduğu bir `CArchive` Kaydet, Farklı Kaydet ve Aç komutlarını Dosya menüsünde adına belgeniz için nesne.  
  
 Kullanıcı, uygulamanızın Dosya menüsünden Kaydet komutu verdiğinde framework yaptığı aşağıda verilmiştir:  
  
1.  Sunan **Kaydet** iletişim kutusu ve kullanıcıdan dosya adını alır.  
  
2.  Kullanıcı tarafından adlı dosyayı açar bir `CFile` nesnesi.  
  
3.  Oluşturur bir `CArchive` için işaret nesnesi `CFile` nesnesi. Oluşturma `CArchive` nesne framework ayarlar "depolamak için" modunu (yazma, seri hale), "Yük" aksine (okuma, seri durumdan).  
  
4.  Çağrıları `Serialize` tanımlanan işlevi, **CDocument**-türetilmiş sınıf başvurusu geçirme, `CArchive` nesnesi.  
  
 Belgenizin `Serialize` işlevi sonra verileri Yazar `CArchive` kısa süre içinde açıklandığı gibi nesne. Dönüş bağlı, `Serialize` framework işlevi, bozar `CArchive` nesnesi ve ardından `CFile` nesnesi.  
  
 Bu nedenle, oluşturduğunuz iskelet izin verirseniz `CArchive` nesne belgeniz için tüm yapmanız gereken belgenin uygulamak olduğu `Serialize` yazar ve okur ve Arşiv gelen işlev. Uygulamak de `Serialize` herhangi `CObject`-türetilmiş nesneleri, belgenin `Serialize` işlevi sırayla doğrudan veya dolaylı olarak serileştirir.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive nesnesi açık oluşturma  
 Belge çerçeve aracılığıyla seri hale getirme yanı sıra zaman ihtiyacınız olabilecek diğer durumlar vardır bir `CArchive` nesnesi. Örneğin, verileri için ve panodan tarafından temsil edilen seri hale getirmek isteyebilirsiniz bir `CSharedFile` nesnesi. Veya, bir kullanıcı arabirimi çerçevesi tarafından sunulan olandan farklı bir dosya kaydetmek için kullanmak isteyebilirsiniz. Bu durumda, açıkça oluşturabileceğiniz bir `CArchive` nesnesi. Bunu, framework değil, aynı şekilde, aşağıdaki yordamı kullanarak yapabilirsiniz.  
  
#### <a name="to-explicitly-create-a-carchive-object"></a>Açıkça CArchive nesnesi oluşturmak için  
  
1.  Oluşturmak bir `CFile` veya nesneyi türetilen `CFile`.  
  
2.  Geçirmek `CFile` Oluşturucusu nesnesine `CArchive`, aşağıdaki örnekte gösterildiği gibi:  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     İkinci bağımsız değişkeni `CArchive` Oluşturucusu arşive depolama ve veri ya da yükleme dosyasından kullanılıp kullanılmayacağını belirten bir Enum değeri değil. `Serialize` Bir nesnenin işlevini çağırarak bu durum denetler `IsStoring` arşiv nesnesinin işlevi.  
  
 Depolama veya yerel bilgisayardan veya veri yükleme tamamlandığında, `CArchive` nesne, kapatın. Ancak `CArchive` (ve `CFile`) nesneleri otomatik olarak kapatılacak arşiv (ve dosya), Kurtarma hataları kolaylaştırır beri açıkça Bunun iyi bir uygulamadır. Hata işleme hakkında daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
#### <a name="to-close-the-carchive-object"></a>CArchive nesnesi kapatmak için  
  
1.  Aşağıdaki örnekte nasıl kapatılacağını gösterilmektedir `CArchive` nesnesi:  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

