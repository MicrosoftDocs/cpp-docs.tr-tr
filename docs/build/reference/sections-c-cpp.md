---
title: BÖLÜMLER (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c433bf49ee4c56833ac7291bcc4a0f90e32f4e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377306"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
Bir veya daha fazla bölüm tanıtır `definitions` bölümlerde projenizin çıktı dosyasına erişim tanımlayıcıları olan.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her tanım ayrı bir satırda olmalıdır. `SECTIONS` Anahtar sözcüğü veya önceki bir satır ilk tanım aynı satır üzerinde olabilir. Bir veya daha fazla .def dosyası içerebilir `SECTIONS` deyimleri.  
  
 Bu `SECTIONS` deyimi görüntü dosyasında bir veya daha fazla bölümü için öznitelikler ayarlar ve varsayılan öznitelikleri her bölüm türü için geçersiz kılmak için kullanılabilir.  
  
 İçin biçim `definitions` değil:  
  
 `.section_name specifier`  
  
 Burada `.section_name` program görüntünüzü bölümünde adıdır ve `specifier` biri veya birkaçı şu erişim değiştiricileri:  
  
|Değiştirici|Açıklama|  
|--------------|-----------------|  
|`EXECUTE`|Yürütülebilir bir bölümdür|  
|`READ`|Verileri okuma işlemlerine izin verir|  
|`SHARED`|Görüntü yükleme tüm işlemler arasında bölüm paylaşır|  
|`WRITE`|Veri yazma işlemlerinin sağlar|  
  
 Belirleyici adlarının boşlukla ayırın. Örneğin:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS` Bölüm listesini başlangıcını işaretler `definitions`. Her `definition` ayrı bir satırda olmalıdır. `SECTIONS` Anahtar sözcüğü, ilk olarak aynı satırda olabilir `definition` veya önceki bir satır. Bir veya daha fazla .def dosyası içerebilir `SECTIONS` deyimleri. `SEGMENTS` Anahtar sözcüğü eşanlamlısı olarak desteklendiğini `SECTIONS`.  
  
 Visual C++ eski sürümleri desteklenir:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS` Anahtar sözcüğü uyumluluk için desteklenir, ancak göz ardı edilir.  
  
 Bölüm öznitelikleri belirtmek için eşdeğer bir yolu [/SECTION](../../build/reference/section-specify-section-attributes.md) seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)