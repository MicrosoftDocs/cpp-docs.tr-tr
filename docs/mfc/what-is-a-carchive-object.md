---
title: CArchive Nesnesi Nedir?
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 0a78385c81c43a4b0c925bbe89ccd3937873ee8b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446023"
---
# <a name="what-is-a-carchive-object"></a>CArchive Nesnesi Nedir?

`CArchive` nesnesi, bir `CFile` nesnesine veya bir nesne türüne seri hale getirilebilir nesneler yazmak veya okumak için tür açısından güvenli bir arabelleğe alma mekanizması sağlar. Genellikle `CFile` nesnesi bir disk dosyasını temsil eder; Ancak, büyük olasılıkla panoyu temsil eden bir bellek dosyası (`CSharedFile` nesnesi) de olabilir.

Belirli bir `CArchive` nesnesi verileri depolar (Yazar, seri hale getirir) ya da verileri yükler (okur, dizileştirir), ancak her ikisi birden değildir. Bir `CArchive` nesnesinin ömrü, bir dosyaya nesne yazma veya bir dosyadaki nesneleri okuma yoluyla tek bir geçişle sınırlıdır. Bu nedenle, verileri bir dosyaya serileştirmek ve sonra dosyanın geri serisini kaldırmak için, büyük ölçüde oluşturulmuş iki `CArchive` nesne gerekir.

Bir arşiv nesneleri bir dosyaya depoladığında arşiv, `CRuntimeClass` adını nesnelerine ekler. Daha sonra, başka bir arşiv bir dosyadaki nesneleri bellekten belleğe yüklediğinde, `CObject`türetilen nesneler nesnelerin `CRuntimeClass` göre dinamik olarak yeniden yapılandırılır. Verilen bir nesne, depolama arşivi tarafından dosyaya yazıldığı için birden çok kez başvuruda bulunabilir. Ancak, yükleme Arşivi nesneyi yalnızca bir kez yeniden oluşturacak. Bir arşiv 'in nesnelere `CRuntimeClass` bilgileri nasıl iliştirir ve nesneleri yeniden oluşturma hakkında ayrıntılar [teknik notta 2](../mfc/tn002-persistent-object-data-format.md)' de açıklanmıştır.

Veriler bir arşive serileştirildiği için arşiv, arabelleği dolu olana kadar verileri biriktirir. Sonra arşiv, `CArchive` nesnesi tarafından işaret edilen `CFile` nesnesine arabelleğini yazar. Benzer şekilde, bir arşivden verileri okurken, dosyadaki verileri arabelleğinden ve sonra arabelleğinden, seri durumdan çıkarılan nesneniz ile okur. Bu arabelleğe alma, bir sabit diskin fiziksel olarak okuduğu her zaman sayısını azaltır ve bu sayede uygulamanızın performansını geliştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
