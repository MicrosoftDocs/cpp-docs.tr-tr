---
description: 'Hakkında daha fazla bilgi edinin: implementation_only Import özniteliği'
title: implementation_only içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 8afeb9981c5931596fc500419755521a41a3d7c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236548"
---
# <a name="implementation_only-import-attribute"></a>implementation_only içeri aktarma özniteliği

**C++ özel**

`.tlh`Birincil tür kitaplığı üst bilgi dosyasının oluşturulmasını engeller.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **implementation_only**

## <a name="remarks"></a>Açıklamalar

Bu dosya, tür kitaplığı içeriğini göstermek için kullanılan tüm bildirimleri içerir. `.tli`Sarmalayıcı üye işlevlerinin uygulamalarıyla birlikte üstbilgi dosyası oluşturulur ve derlemeye dahil edilir.

Bu öznitelik belirtildiğinde, üst bilginin içeriği, `.tli` üst bilgide normal olarak kullanılan ile aynı ad alanıdır `.tlh` . Ayrıca, üye işlevleri satır içi olarak bildirilmez.

**İmplementation_only** özniteliği, uygulamaları ön derlenmiş ÜSTBILGI (pch) dosyasının dışına tutmanın bir yolu olarak [no_implementation](../preprocessor/no-implementation.md) özniteliğiyle birlikte kullanılmak üzere tasarlanmıştır. `#import`Özniteliği içeren bir ifade, `no_implementation` PCH 'yi oluşturmak için kullanılan kaynak bölgeye yerleştirilir. Elde edilen PCH, bir dizi kaynak dosya tarafından kullanılır. `#import` **İmplementation_only** özniteliğine sahip BIR ifade, PCH bölgesinin dışında kullanılır. Bu ifadeyi kaynak dosyalardan birinde yalnızca bir kez kullanmanız gerekir. Her kaynak dosya için ek yeniden derleme gerekmeden tüm gerekli sarmalayıcı üye işlevlerini oluşturur.

> [!NOTE]
> Bir deyimdeki **implementation_only** özniteliği, `#import` özniteliğiyle birlikte `#import` aynı tür kitaplığına sahip başka bir deyimle birlikte kullanılmalıdır `no_implementation` . Aksi takdirde, derleyici hataları oluşturulur. Bunun nedeni, deyimin tarafından oluşturulan sarmalayıcı sınıf tanımlarının, `#import` `no_implementation` **implementation_only** özniteliği tarafından oluşturulan uygulamaları derlemek için gereklidir.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
