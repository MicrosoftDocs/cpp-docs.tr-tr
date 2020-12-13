---
description: 'Hakkında daha fazla bilgi edinin: CArchive nesnesi nedir?'
title: CArchive Nesnesi Nedir?
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 7d98200f87f4b428a9450894aca5f8958115d627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142798"
---
# <a name="what-is-a-carchive-object"></a>CArchive Nesnesi Nedir?

Bir `CArchive` nesne, bir nesne üzerinde veya nesnesinden seri hale getirilebilir nesneler yazmak veya okumak için tür açısından güvenli bir arabelleğe alma mekanizması sağlar `CFile` . Genellikle `CFile` nesne bir disk dosyasını temsil eder; ancak, büyük `CSharedFile` olasılıkla panoyu temsil eden bir bellek dosyası (nesne) de olabilir.

Belirli bir `CArchive` nesne verileri depolar (Yazar, seri hale getirir) ya da verileri yükler (okur, dizileştirir), ancak her ikisi birden değildir. Bir nesnenin yaşam süresi bir `CArchive` dosyaya nesne yazma veya bir dosyadaki nesneleri okuma ile sınırlıdır. Bu nedenle, `CArchive` verileri bir dosyaya serileştirmek ve sonra dosyanın geri serisini kaldırmak için, yoğun olarak oluşturulan iki nesne gerekir.

Bir arşiv nesneleri bir dosyaya depoladığında arşiv, bu `CRuntimeClass` adı nesnelerine ekler. Daha sonra, başka bir arşiv bir dosyadaki nesneleri bellekten belleğe yüklediğinde, `CObject` -türetilmiş nesneler nesnelerine göre dinamik olarak yeniden yapılandırılır `CRuntimeClass` . Verilen bir nesne, depolama arşivi tarafından dosyaya yazıldığı için birden çok kez başvuruda bulunabilir. Ancak, yükleme Arşivi nesneyi yalnızca bir kez yeniden oluşturacak. Bir arşiv `CRuntimeClass` 'in nesnelere bilgi iliştirme ve nesneleri yeniden oluşturma hakkındaki ayrıntılar [teknik notta 2](../mfc/tn002-persistent-object-data-format.md)' de açıklanmıştır.

Veriler bir arşive serileştirildiği için arşiv, arabelleği dolu olana kadar verileri biriktirir. Sonra arşiv, arabelleğini `CFile` nesne tarafından işaret edilen nesneye yazar `CArchive` . Benzer şekilde, bir arşivden verileri okurken, dosyadaki verileri arabelleğinden ve sonra arabelleğinden, seri durumdan çıkarılan nesneniz ile okur. Bu arabelleğe alma, bir sabit diskin fiziksel olarak okuduğu her zaman sayısını azaltır ve bu sayede uygulamanızın performansını geliştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
