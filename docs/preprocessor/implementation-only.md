---
title: implementation_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- implementation_only
dev_langs:
- C++
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a2cbf0b39dc1c5f5462ae105e2206d70a38f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="implementationonly"></a>implementation_only
**C++ özel**  
  
 .Tlh üstbilgi dosyası (birincil üstbilgi dosyası) oluşturulmasını engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu dosya türü kitaplığı içeriği kullanıma sunmak için kullanılan tüm bildirimleri içerir. Sarmalayıcı üye işlevleri uygulamalarıyla birlikte .tli üstbilgi dosyası oluşturulur ve derlemede dahil.  
  
 Bu öznitelik belirtilmediğinde .tli üstbilgisinin içeriğini normal olarak .tlh üstbilgisinde kullanılanla aynı ad kullanılıyor. Ayrıca, üye işlevleri satır içi olarak bildirilmemiş.  
  
 `implementation_only` Özniteliği ile birlikte kullanılmak için tasarlanmıştır [no_implementation](../preprocessor/no-implementation.md) uygulamaları önceden derlenmiş üstbilgi (PCH) dosyasının dışında tutulması bir yolu olarak özniteliği. Bir `#import` deyimiyle `no_implementation` özniteliği PCH oluşturmak için kullanılan kaynak bölgede yerleştirilir. Sonuçta elde edilen PCH kaynak dosyalarını bir dizi tarafından kullanılır. Bir `#import` deyimiyle `implementation_only` özniteliği PCH bölgesinin dışındaki sonra kullanılır. Bu deyim yalnızca bir kez kaynak dosyalarından birini kullanmak için gerekli değildir. Bu, her kaynak dosya için ek gerekmeksizin tüm gerekli sarmalayıcı üye işlevleri oluşturur.  
  
> [!NOTE]
>  `implementation_only` Bir öznitelik `#import` deyimi başka ile birlikte olmalıdır `#import` aynı deyimi türünü Kitaplığı `no_implementation` özniteliği. Aksi takdirde derleyici hataları oluşturulur. Sarmalayıcı sınıf tanımları tarafından oluşturulan olmasıdır `#import` deyimiyle `no_implementation` özniteliği tarafından oluşturulan uygulamaları derlemek için gerekli `implementation_only` özniteliği.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)