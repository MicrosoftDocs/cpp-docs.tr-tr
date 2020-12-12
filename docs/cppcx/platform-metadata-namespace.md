---
description: 'Daha fazla bilgi edinin: Platform:: Metadata ad alanı'
title: 'Platform:: Metadata ad alanı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 5dd699c0136c4ee37462dd22f9ee27bec345e8b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308399"
---
# <a name="platformmetadata-namespace"></a>Platform:: Metadata ad alanı

Bu ad alanı, türlerin bildirimlerini değiştiren öznitelikler içerir.

## <a name="syntax"></a>Syntax

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>Üyeler

Bu ad alanı iç kullanım için tasarlanmış olsa da, tarayıcılar bu ad alanının aşağıdaki üyelerini görüntüleyebilir.

|Ad|Görüyorum|
|----------|------------|
|Öznitelik|Öznitelikler için temel sınıf.|
|[Platform:: Metadata::D efaultMemberAttribute özniteliği](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Birkaç olası aşırı yüklenmiş işlev arasında çağrılacak tercih edilen işlevi gösterir.|
|[Platform:: Metadata:: FlagsAttribute özniteliği](../cppcx/platform-metadata-flagsattribute-attribute.md) Larına|Bir numaralandırmayı bit alanları numaralandırması olarak bildirir.<br /><br /> Aşağıdaki örnek, bir numaralandırma için özniteliği nasıl uygulayacağınızı gösterir `Flags` .<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform:: Metadata:: RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Özel bir başvuru sınıfının geçerli bir çalışma zamanı sınıf adına sahip olmasını sağlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Platform`

### <a name="requirements"></a>Gereksinimler

**Meta veri:** platform. winmd

**Ad alanı:** Platform:: Metadata

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
