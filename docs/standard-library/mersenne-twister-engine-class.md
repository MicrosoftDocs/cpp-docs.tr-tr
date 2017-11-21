---
title: "mersenne_twister_engine sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::mersenne_twister_engine
dev_langs: C++
helpviewer_keywords: mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58a777a049b270702e63391ebc7bd4c1addc3b32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mersennetwisterengine-class"></a>mersenne_twister_engine Sınıfı
Mersenne twister algoritmadan yola çıkılarak tamsayılar yüksek kaliteli rastgele dizisini oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class UIntType,   
    size_t W, size_t N, size_t M, size_t R,  
    UIntType A, size_t U, UIntType D, size_t S,  
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>  
class mersenne_twister_engine;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `UIntType`  
 İşaretsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
 `W`  
 **Word boyutu**. Her sözcüğün durumu dizisi bit cinsinden boyutu. **Önkoşul**:`2u < W ≤ numeric_limits<UIntType>::digits`  
  
 `N`  
 **Durum boyutu**. Durum dizisi (değerler) öğe sayısı.  
  
 `M`  
 **Kaydırma boyutu**. Her geçiş sırasında atlamak için öğe sayısı. **Önkoşul**:`0 < M ≤ N`  
  
 `R`  
 **Bit maskesi**. **Önkoşul**:`R ≤ W`  
  
 `A`  
 **XOR maskesi**. **Önkoşul**:`A ≤ (1u<<W) - 1u`  
  
 `U`, `S`, `T`, `L`  
 **Shift parametreleri tempering**. Shift değerleri olarak (tempering) karıştırma sırasında kullanılır. Önkoşul:`U,S,T,L ≤ W`  
  
 `D`, `B`, `C`  
 **Bit maskesi parametreleri tempering**. Bit maskesi değerleri (tempering) karıştırma sırasında kullanılır. Önkoşul:`D,B,C ≤ (1u<<W) - 1u`  
  
 `F`  
 **Başlatma çarpanı**. İle dizisi başlatma yardımcı olmak için kullanılır. Önkoşul:`F ≤ (1u<<W) - 1u`  
  
## <a name="members"></a>Üyeler  
  
||||  
|-|-|-|  
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|  
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|  
  
 `default_seed`üye sabit, tanımlanmış olarak `5489u`, varsayılan parametre değeri olarak kullanılan `mersenne_twister_engine::seed` ve tek değer Oluşturucusu.  
  
 Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıfı kapalı aralıkta değerler döndüren bir rastgele bir sayı altyapısı açıklar [ `0`, `2` <sup>W</sup> - `1`]. Büyük tam sayı değerine sahip tutan `W * (N - 1) + R` BITS. Ayıklar `W` birer birer bu büyük değer ve tüm BITS kullandığında BITS kaydırma ve BITS ayıklamak için yeni bir dizi sahip olması BITS karıştırma büyük değer twists onu. Son altyapının durumunda `N` `W`-bit, kullanılan değerler `operator()` en az adlı `N` zaman, aksi takdirde `M` `W`-bit kullanılmış değerleri ve son `N - M` değerleri Çekirdek.  
  
 Oluşturucunun shift değerleri tarafından tanımlanan bir bükümlü genelleştirilmiş geri bildirim shift kayıt kullanarak tutan büyük değer twists `N` ve `M`, bir geçiş değer `R`ve bir koşullu XOR maskesi `A`. BITS ham shift kaydının (değerleri tarafından tanımlanan bir bit karıştırma matris göre tempered) ek olarak, karıştırılmış `U`, `D`, `S`, `B`, `T`, `C`, ve `L`.  
  
 Şablon bağımsız değişken `UIntType` değerleri kadar tutmaya yetecek büyüklükte olmalıdır `2` <sup>W</sup> - `1`. , Başka bir şablon bağımsız değişken değerlerini aşağıdaki gereksinimleri karşılaması gerekir: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.  
  
 Bu altyapısından bir oluşturucuyu doğrudan oluşturabileceğiniz rağmen önceden tanımlanmış bu tür tanımları birini kullanmanız önerilir:  
  
 `mt19937`: 32-bit Mersenne twister altyapısı (Matsumoto ve Nishimura, 1998).  
  
```  
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,   
    31, 0x9908b0df,   
    11, 0xffffffff,   
    7, 0x9d2c5680,   
    15, 0xefc60000,   
    18, 1812433253> mt19937;  
```  
  
 `mt19937_64`: 64-bit Mersenne twister altyapısı (Matsumoto ve Nishimura, 2000).  
  
```  
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,   
    31, 0xb5026f5aa96619e9ULL,   
    29, 0x5555555555555555ULL,   
    17, 0x71d67fffeda60000ULL,   
    37, 0xfff7eee000000000ULL,   
    43, 6364136223846793005ULL> mt19937_64;  
```  
  
 Wikipedia makaleyi Mersenne twister algoritması hakkında ayrıntılı bilgi için bkz: [Mersenne twister](http://go.microsoft.com/fwlink/LinkId=402356).  
  
## <a name="example"></a>Örnek  
 Kod örneği için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)

