---
title: Parametre öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], parameter attributes
- parameter attributes
ms.assetid: 024c2dd5-49d7-4ced-a17a-c56c1bc485b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa757834e61dab89ce6ff4682bd9a390c9b650bf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598703"
---
# <a name="parameter-attributes"></a>Parametre Öznitelikleri

Bir sınıf veya arabirim yönteminin parametreleri aşağıdaki özniteliklere uygulanır.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[defaultvalue](../windows/defaultvalue.md)|Belirtilmiş bir isteğe bağlı parametre için bir varsayılan değer belirtimi sağlar.|
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[iid_is](../windows/iid-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[immediatebind](../windows/immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|
|[in](../windows/in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|
|[last_is](../windows/last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[lcid](../windows/lcid.md)|Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.|
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[İsteğe bağlı](../windows/optional-cpp.md)|Bir üye işlev için isteğe bağlı bir parametre belirtir.|
|[out](../windows/out-cpp.md)|Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.|
|[Aralığı](../windows/range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[ref](../windows/ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[retval](../windows/retval.md)|Üyenin dönüş değerini alan parametreyi belirler.|
|[satype](../windows/satype.md)|Veri türü belirtir `SAFEARRAY` yapısı.|
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[benzersiz](../windows/unique-cpp.md)|Bir benzersiz işaretçi belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)