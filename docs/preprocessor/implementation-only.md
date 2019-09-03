---
title: implementation_only içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 08144b3c815350acfe6a856b36d2d88085d1c04d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218979"
---
# <a name="implementation_only-import-attribute"></a>implementation_only içeri aktarma özniteliği

**C++Belirli**

`.tlh` Birincil tür kitaplığı üst bilgi dosyasının oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **implementation_only**

## <a name="remarks"></a>Açıklamalar

Bu dosya, tür kitaplığı içeriğini göstermek için kullanılan tüm bildirimleri içerir. Sarmalayıcı üye işlevlerinin uygulamalarıyla birlikte üstbilgidosyasıoluşturulurvederlemeyedahiledilir.`.tli`

Bu öznitelik belirtildiğinde, `.tli` üst bilginin içeriği, `.tlh` üst bilgide normal olarak kullanılan ile aynı ad alanıdır. Ayrıca, üye işlevleri satır içi olarak bildirilmez.

**İmplementation_only** özniteliği, uygulamaları ön derlenmiş ÜSTBILGI (pch) dosyasından tutmanın bir yolu olarak [no_implementation](../preprocessor/no-implementation.md) özniteliğiyle birlikte kullanılmak üzere tasarlanmıştır. Özniteliği içeren bir `#import` ifade, PCH 'yi oluşturmak için kullanılan kaynak bölgeye yerleştirilir. `no_implementation` Elde edilen PCH, bir dizi kaynak dosya tarafından kullanılır. İmplementation_only `#import` özniteliğine sahip bir ifade, PCH bölgesinin dışında kullanılır. Bu ifadeyi kaynak dosyalardan birinde yalnızca bir kez kullanmanız gerekir. Her kaynak dosya için ek yeniden derleme gerekmeden tüm gerekli sarmalayıcı üye işlevlerini oluşturur.

> [!NOTE]
> `#import` `no_implementation` Bir `#import` deyimdeki implementation_only Özniteliği, özniteliği ile aynı tür kitaplığının başka bir ifadesiyle birlikte kullanılmalıdır. Aksi takdirde, derleyici hataları oluşturulur. Bunun nedeni, `#import` deyimin `no_implementation` tarafından oluşturulan sarmalayıcı sınıf tanımlarının, **implementation_only** özniteliği tarafından oluşturulan uygulamaları derlemek için gerekli olmasından kaynaklanır.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
