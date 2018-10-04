---
title: Parametre öznitelikleri (C++ COM) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], parameter attributes
- parameter attributes
ms.assetid: 024c2dd5-49d7-4ced-a17a-c56c1bc485b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 160e71111a9080367390302a59c41a53580ffe0b
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789841"
---
# <a name="parameter-attributes"></a>Parametre Öznitelikleri

Bir sınıf veya arabirim yönteminin parametreleri aşağıdaki özniteliklere uygulanır.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[defaultvalue](defaultvalue.md)|Belirtilmiş bir isteğe bağlı parametre için bir varsayılan değer belirtimi sağlar.|
|[first_is](first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[iid_is](iid-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[immediatebind](immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|
|[in](in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|
|[last_is](last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[lcid](lcid.md)|Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[İsteğe bağlı](optional-cpp.md)|Bir üye işlev için isteğe bağlı bir parametre belirtir.|
|[out](out-cpp.md)|Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.|
|[Aralığı](range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[ref](ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[retval](retval.md)|Üyenin dönüş değerini alan parametreyi belirler.|
|[satype](satype.md)|Veri türü belirtir `SAFEARRAY` yapısı.|
|[size_is](size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[benzersiz](unique-cpp.md)|Bir benzersiz işaretçi belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)