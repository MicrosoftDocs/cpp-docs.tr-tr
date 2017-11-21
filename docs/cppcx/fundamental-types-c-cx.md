---
title: "Temel türler (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 1984ba2b2291c14403af1237a9c990de2c0e0217
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fundamental-types-ccx"></a>Temel türler (C + +/ CX)
Ek olarak standart C++ yerleşik türleri, C + +/ CX destekleyen standart C++ türleri eşlenen temel Windows çalışma zamanı türleri için tür tanımları sağlayarak Windows çalışma zamanı mimarisi tarafından tanımlanan tür sistemi... C + +/ CX Boolean, karakter ve sayısal temel türleri uygular. Bu tür tanımları tanımlanan `default` ad alanı hiçbir zaman açıkça belirtilmesi gerekiyor. Ayrıca, C + +/ CX, sarmalayıcıları ve somut uygulamaları belirli Windows çalışma zamanı türleri ve arabirimleri sağlar.  
  
## <a name="boolean-and-character-types"></a>Boolean ve karakter türleri  
 Aşağıdaki tabloda yerleşik Boolean ve karakter türleri ve standart C++ eşdeğerleri listeler.  
  
|Ad Alanı|C + +/ CX adı|Tanım|Standart C++ adı|Aralık, değerleri|  
|---------------|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|  
|Platform|Boole değeri|Bir 8 bit Boole değeri.|bool|`true`(sıfır) ve `false` (sıfır)|  
|default|char16|Unicode (UTF-16) kod noktası temsil eden bir 16 bit sayısal olmayan değer.|wchar_t<br /><br /> veya<br /><br /> L'c'|(Unicode standart tarafından belirtilen)|  
  
## <a name="numeric-types"></a>Sayısal türler  
 Aşağıdaki tabloda yerleşik sayısal türler listelenmektedir. Sayısal türler içinde bildirilen `default` karşılık gelen C++ yerleşik türü için tür tanımları ad alanı ve şunlardır. Windows çalışma zamanı'nda (örneğin, uzun) tüm C++ yerleşik türleri desteklenir. Tutarlılık ve daha anlaşılır olması için C + kullanmanızı öneririz +/ CX adı.  
  
|C + +/ CX adı|Tanım|Standart C++ adı|Aralık, değerleri|  
|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|  
|int8|Bir 8 bit imzalı sayısal değer.|İmzalı char|-128 127 aracılığıyla|  
|uint8|Bir 8 bit işaretsiz sayısal değer.|unsigned char|0 ile 255|  
|Int16|Bir 16 bit işaretli tamsayıyı.|short|-32.768 32.767 aracılığıyla|  
|uint16|Bir 16 bit işaretsiz tamsayı.|imzasız short|0 ile 65.535|  
|Int32|32 bit imzalı bir tamsayı.|int|-2.147.483.648 2.147.483.647 aracılığıyla|  
|uint32|Bir 32 bit işaretsiz tamsayı.|unsigned int|0 ile 4.294.967.295 arasında|  
|Int64|64-bit imzalı bir tamsayı.|uzun uzun - veya - __int64|-9,223,372,036,854, 9,223,372,036,854,775,807 aracılığıyla 775,808|  
|uint64|Bir 64-bit işaretsiz tamsayı.|İmzasız long uzun - veya - imzasız __int64|0 ile 18,446,744,073,709,551,615|  
|Float32|Bir 32 bit IEEE 754 kayan noktalı sayı.|float|3.4e +/-38 (7 basamak)|  
|Float64|Bir 64-bit IEEE 754 kayan noktalı sayı.|çift|1.7E +/-308 (15 basamak)|  
  
## <a name="windows-runtime-types"></a>Windows çalışma zamanı türleri  
 Aşağıdaki tabloda, Windows çalışma zamanı mimarisi tarafından tanımlanır ve C + içinde yerleşik olan bazı ek türleri listelenmektedir +/ CX. Nesne ve dize başvuru türleridir. Diğer değer türleridir. Bu türdeki tüm içinde bildirilen `Platform` ad alanı. Tam listesi için bkz: [Platform ad alanı](../cppcx/platform-namespace-c-cx.md).  
  
|Ad|Tanım|  
|----------|----------------|  
|Nesne|Herhangi bir Windows çalışma zamanı türü temsil eder.|  
|Dize|Bir metin temsil karakter dizisi.|  
|Rect|Dikdörtgene boyutunu ve konumunu temsil eden dört kayan nokta sayıları kümesi.|  
|SizeT|Sıralı bir çifti kayan noktalı sayıların yüksekliğini ve genişliğini belirtin.|  
|noktası|Kayan nokta x koordinatlarına iki boyutlu bir düzlem bir nokta tanımlayan y koordinatları ve sıralı çifti.|  
|Guid|Benzersiz bir tanımlayıcı olarak kullanılan bir 128-bit sayısal olmayan değer.|  
|UIntPtr|(Yalnızca iç kullanım için.) İşaretçi olarak kullanılan imzasız bir 64-bit değeri.|  
|IntPtr|(Yalnızca iç kullanım için.)  İşaretçi olarak kullanılan 64-bit imzalı bir değer.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)