---
title: Platform::metadata Namespace
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 39a4709c8f66c4dcc2ee5185f2a1df27b0666445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462874"
---
# <a name="platformmetadata-namespace"></a>Platform::metadata Namespace

Bu ad alanı türlerinin bildirimlerini değiştirme öznitelikleri içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>Üyeler

Bu ad dahili kullanım içindir ancak tarayıcılar bu ad aşağıdaki üyeleri görüntüleyebilir.

|Ad|Açıklama|
|----------|------------|
|Öznitelik|Öznitelikleri için temel sınıfı.|
|[Platform::Metadata::DefaultMemberAttribute Özniteliği](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Birkaç olası aşırı yüklenmiş işlevleri çağırmak için tercih edilen işlev gösterir.|
|[Platform::metadata:: FlagsAttribute özniteliği](../cppcx/platform-metadata-flagsattribute-attribute.md)bayrakları|Sabit bir numaralandırma bit alanları olarak bildirir.<br /><br /> Aşağıdaki örnek nasıl uygulanacağını gösterir `Flags` numaralandırma özniteliği.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform::metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Özel bir başvuru sınıfı, geçerli çalışma zamanı sınıf adı sahip olmasını sağlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Platform`

### <a name="requirements"></a>Gereksinimler

**Meta veri:** platform.winmd

**Namespace:** Platform::Metadata

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)