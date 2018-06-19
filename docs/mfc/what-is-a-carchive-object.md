---
title: CArchive nesnesi nedir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55b97843a8aeb2599d2bdf34458b362fc5899368
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383840"
---
# <a name="what-is-a-carchive-object"></a>CArchive Nesnesi Nedir?
A `CArchive` nesnesi, gelen veya giden serileştirilebilir nesneler okuma veya yazma için bir tür kullanımı uyumlu arabelleğe alma mekanizması sağlar bir `CFile` nesnesi. Genellikle `CFile` nesnesini temsil eden bir disk dosyası; ancak, bu da bellek dosyasını olabilir (`CSharedFile` nesnesi), belki de Pano temsil eden.  
  
 Belirli bir `CArchive` ya da depoları nesne (yazar, serileştiren) veri ya da yükler (okuma, seri durumdan çıkarır) verileri, ancak hiçbir zaman hem de. Ömrünü bir `CArchive` nesneleri bir dosyaya yazmak veya bir dosyadan nesneler okunurken aracılığıyla bir geçişine nesne sınırlıdır. Bu nedenle, iki sırayla oluşturulan `CArchive` nesneleri, verileri bir dosyaya seri hale getirmek ve geri dosyasından serisini kaldırmak için gereklidir.  
  
 Bir arşiv dosyasına nesneleri depoladığında, arşiv iliştirir `CRuntimeClass` nesnelere adı. Sonra başka bir arşiv nesneleri bellek için bir dosyadan yüklediğinde `CObject`-türetilen nesneler dinamik olarak yeniden göre `CRuntimeClass` nesneleri. Tarafından depolanmasını arşiv dosyasına yazılır gibi belirli bir nesne birden çok kez başvurulabilir. Arşiv yüklenirken, ancak nesne yalnızca bir kez yeniden. Bir arşiv nasıl iliştirir hakkında ayrıntılı bilgi `CRuntimeClass` ve yeniden yapılandırır nesneleri, birden fazla başvuru olası dikkate alarak bilgileri açıklanmıştır [Teknik Not 2](../mfc/tn002-persistent-object-data-format.md).  
  
 Verileri arşive seri olarak arabelleğini dolana kadar arşiv verileri toplanır. Arşiv kendi arabelleğe Yazar sonra `CFile` tarafından için nesne işaret `CArchive` nesnesi. Arşivden verileri okurken benzer şekilde, bu veri arabelleğini dosyasına ve ardından seri durumdan çıkarılmış nesne arabelleğe okur. Bu arabelleğe alma, bir sabit disk fiziksel olarak, bu nedenle, uygulamanızın performansını iyileştirme okunur sayısını azaltır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

