---
title: "Parametre geçirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0359a6cbbb1f646432b03722cdf4ba3010cffa72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="parameter-passing"></a>Parametre Geçirme
Yazmaçları ilk dört tamsayı bağımsız değişken geçirildi. Tamsayı değerleri (sırayla soldan sağa) RCX, RDX, R8 ve R9 geçirilir. Bağımsız değişkenler beş ve daha yüksek yığında geçirilir. Yazmaçları sağa hizalı tüm bağımsız değişkenler. Aranan kaydının üst BITS yoksayabilirsiniz şekilde yapılır olması ve yalnızca gerekli kayıt bölümü erişebilirsiniz.  
  
 Kayan nokta ve çift duyarlıklı bağımsız değişkenler XMM0'geçirilen - normalde bu Kardinal yuvası olması için kullanılacak tamsayı yuvası (RCX, RDX, R8 ve R9) ile (4 kadar) XMM3 göz ardı (örneğe bakın) ve tersi.  
  
 [__m128](../cpp/m128.md) türleri, dizileri ve dizeleri asla geçirilir anlık değere göre ancak bunun yerine bir işaretçi çağıran tarafından ayrılan bellek geçirilir. Aynı boyutta tamsayılar değilmiş gibi yapılar/birleşmeler boyutu 8, 16, 32 veya 64 bit ve __m64 geçirilir. Yapılar/birleşmeler bu boyutları dışında çağıran tarafından ayrılan bellek için bir işaretçi olarak geçirilir. Bu toplama türleri için bir işaretçi olarak geçirilen (de dahil olmak üzere \__m128), çağıran tarafından ayrılan geçici bellek 16 bayt hizalı olacaktır.  
  
 Yığın alanı tahsis etmeyin ve diğer işlevleri çağırmayın iç işlevler diğer geçici kayıtları derleyici ve iç işlev uygulama arasında sıkı bir bağ olduğundan ek kayıt bağımsız değişkenleri geçirmek için kullanabilirsiniz. Bu, performansı artırmak için ek bir fırsattır.  
  
 Aranan kayıt parametrelerini gerekirse kendi gölge alanına dökme sorumluluğunu sahiptir.  
  
 Parametrelerin nasıl geçirildiğini aşağıdaki tabloda özetlenmiştir:  
  
|Parametre türü|Nasıl geçti|  
|--------------------|----------------|  
|Kayan nokta|İlk 4 parametre - XMM0 ila XMM3. Diğerleri yığın olarak geçirilir.|  
|Tamsayı|İlk 4 parametre - RCX, RDX, R8 R9. Diğerleri yığın olarak geçirilir.|  
|Toplamlar (8, 16, 32 veya 64 bit) ve __m64|İlk 4 parametre - RCX, RDX, R8 R9. Diğerleri yığın olarak geçirilir.|  
|Toplamlar (diğer)|İşaretçi. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçileri olarak geçirildi|  
|__m128|İşaretçi. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçileri olarak geçirildi|  
  
## <a name="example-of-argument-passing-1---all-integers"></a>Bağımsız değişken 1 - tüm tamsayılar geçirme örneği  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-2---all-floats"></a>Bağımsız değişken 2 - tüm float geçirme örneği  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Bağımsız değişken geçirme 3 - karma ints ve float örneği  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Bağımsız değişken 4 geçirme örneği-__m64, \__m128 ve toplamalar  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)