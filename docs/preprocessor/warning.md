---
title: Uyarı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- warning_CPP
- vc-pragma.warning
dev_langs:
- C++
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b739a3f72416b6ab58cbdba45a496e10fef4424
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842969"
---
# <a name="warning-pragma"></a>warning Pragması
Derleyici Uyarısı iletilerinin davranışını seçmeli değiştirilmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
#pragma warning(   
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## <a name="remarks"></a>Açıklamalar  
Aşağıdaki uyarı belirleyici parametreleri kullanılabilir.  
  
|Uyarı belirticisi|Açıklama|  
|------------------------|-------------|  
|`1, 2, 3, 4`|Belirtilen düzeyi için belirtilen uyarı geçerlidir. Bu da varsayılan olarak kapalıdır belirtilen bir uyarı açar.|  
|`default`|Uyarı davranış varsayılan değeri sıfırlayın. Bu da varsayılan olarak kapalıdır belirtilen bir uyarı açar. Uyarı, varsayılan olarak oluşturulan, belgelenen, düzeyi.<br /><br /> Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|`disable`|Belirtilen uyarı iletilerini sorun değil.|  
|`error`|Belirtilen uyarıları hata olarak bildirin.|  
|`once`|Belirtilen iletileri yalnızca bir kez görüntüler.|  
|`suppress`|Pragma geçerli durumunu yığına, sonraki satıra için belirtilen uyarı devre dışı bırakır ve böylece pragma durumu sıfırlamaya uyarı yığını açılır.|  
  
 Aşağıdaki kod açıklaması gösterilmektedir bir `warning-number-list` parametresi birden çok uyarı numaralarını ve bu birden çok içerebilir `warning-specifier` parametreleri aynı pragma yönergesi belirtilebilir.  
  
```cpp  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 Bu aşağıdaki kodu işlevsel olarak eşdeğerdir.  
  
```cpp  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 Derleyici 0-999 aralığında olan herhangi bir uyarı sayı 4000 ekler.  
  
 Kod oluşturma ile ilişkili olanlar olan 4700-4999 aralığında uyarı numaraları için yürürlükte derleyici açık kuşak işlevinin karşılaştığında uyarı durumuna işlevi geri kalanı için uygulanmaz. Kullanarak `warning` pragma 4699 daha büyük bir sayı olan bir uyarı durumunu değiştirmek için işlevinde yalnızca kazanacak işlevi sonunda. Aşağıdaki örnek, doğru yerleşimini gösterir `warning` bir kod oluşturma uyarı iletisi devre dışı bırakmak için pragmaları ve ardından geri yüklemek için.  
  
```cpp  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 Bir işlev boyunca, son ayarını gövde dikkat edin `warning` pragma tüm işlevi için geçerli olacaktır.  
  
## <a name="push-and-pop"></a>Anında iletme ve Pop  
 `warning` Pragma de destekler aşağıdaki sözdizimini, burada `n` uyarı düzeyi (1-4 arası) temsil eder.  
  
 `#pragma warning( push [ , n ] )`  
  
 `#pragma warning( pop )`  
   
 Pragma `warning( push )` her uyarı için geçerli uyarı durumu depolar. Pragma `warning( push, n )` her uyarı için geçerli durum depolar ve genel uyarı düzeyi ayarlar `n`.  
  
 Pragma `warning( pop )` POP son uyarı durumuna yığına gönderilir. Uyarı durumu arasında yapılan tüm değişiklikler `push` ve `pop` geri alınır. Bu örneği göz önünde bulundurun:  
  
```cpp  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 Bu kod, sonunda `pop` her uyarı durumunu geri yükler (4705, 4706 ve 4707 içerir) kod başlangıcında neydi için.  
  
 Üstbilgi dosyaları yazdığınızda, kullanabileceğiniz `push` ve `pop` bir kullanıcı tarafından yapılan uyarı durumu değişiklikleri üstbilgileri doğru derleme engellemez olduğunu güvence altına almak için. Kullanım `push` üstbilgi başlangıcında ve `pop` sonunda. Örneğin, düzgün bir şekilde 4 uyarı düzeyinde derlenmiyor bir üstbilgi varsa, aşağıdaki kod 3 uyarı düzeyini değiştirmek ve özgün uyarı düzeyi üstbilgisi sonundaki geri yükleme.  
  
```cpp  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 Uyarılar, yardımcı olan seçeneklerdir bastırmak derleyici hakkında daha fazla bilgi için bkz: [/FI](../build/reference/fi-name-forced-include-file.md) ve [/w](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)