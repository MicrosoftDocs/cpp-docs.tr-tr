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
ms.openlocfilehash: fe45b3e5444549001990f62db7028f9de6d49986
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409669"
---
# <a name="what-is-a-carchive-object"></a>CArchive Nesnesi Nedir?

A `CArchive` nesnesi gelen veya giden serileştirilebilir nesneler okuma veya yazma için bir tür kullanımı uyumlu arabelleğe alma mekanizması sağlar bir `CFile` nesne. Genellikle `CFile` nesnesini temsil eden bir disk dosyası; ancak, da bellek dosyası olabilir (`CSharedFile` nesne), belki de Pano temsil eden.

Belirli bir `CArchive` ya da depoları nesnesi (yazar, serileştiren) veri veya yükler (okuma, seri durumdan çıkarır) verileri, ancak hiçbir zaman hem de. Ömrü boyunca bir `CArchive` nesnedir nesneleri bir dosyaya yazmak veya nesneleri Dosyadan okuma aracılığıyla tek seferde sınırlıdır. Bu nedenle, iki sırayla oluşturulan `CArchive` nesneleri, verileri bir dosyaya seri hale getirme ve dosyasından serisini kaldırmak için gereklidir.

Bir arşiv nesneleri bir dosyaya depoladığında, arşiv ekler `CRuntimeClass` nesnelere adı. Sonra başka bir arşiv nesneleri bellekte, bir dosya yüklendiğinde `CObject`-türetilmiş nesneler dinamik olarak yeniden göre `CRuntimeClass` nesne. Depolama arşivi dosyaya yazılır gibi belirli bir nesne birden çok kez başvurulabilir. Arşiv yüklenirken, ancak nesne yalnızca bir kez yeniden. Bir arşiv nasıl ekleyen hakkında ayrıntılar `CRuntimeClass` bilgilerini nesneleri ve birden fazla başvuru olası dikkate alarak, yeniden yapılandırır nesneler açıklanmıştır [Teknik Not 2](../mfc/tn002-persistent-object-data-format.md).

Bir arşiv verileri seri hale getirilmiş gibi kendi arabellek dolana kadar arşiv verileri toplanır. Arşiv, arabelleğe Yazar sonra `CFile` nesne tarafından işaret edilen `CArchive` nesne. Arşivden veri okuma gibi benzer şekilde, bu verileri, arabellek dosyaya ve ardından, seri durumdan çıkarılmış nesne arabelleğe okur. Bu arabelleğe alma, bu nedenle, uygulamanızın performansını iyileştirme, bir sabit diski fiziksel olarak okunur sayısını azaltır.

## <a name="see-also"></a>Ayrıca Bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

