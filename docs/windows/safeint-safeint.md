---
title: SafeInt::SafeInt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7154349105c1953ad314b7928e7be8385179c42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888753"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
Oluşturan bir `SafeInt` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `i`  
 Yeni değeri `SafeInt` nesnesi. Bu oluşturucu bağlı olarak T veya U türünde bir parametresi olmalıdır.  
  
 [in] `b`  
 Yeni için Boolean değeri `SafeInt` nesnesi.  
  
 [in] `u`  
 A `SafeInt` türüne Yeni `SafeInt` nesnesi aynı değere sahip `u`, ancak türü t olur  
  
 U  
 Depolanan verilerin türünü `SafeInt`. Bu bir Boole değeri, karakter veya tamsayı türünde olabilir. Bir tamsayı türü ise, yeniden imzalı imzasız veya bırakılabilir ve 8 ve 64 bit arasında olmalıdır.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon türleri hakkında daha fazla bilgi için `T` ve `E`, bkz: [SafeInt sınıfı](../windows/safeint-class.md).  
  
 Giriş parametresi oluşturucusu için `i` veya `u`, bir Boole değeri, karakter veya tamsayı türünde olmalıdır. Parametresi, başka bir tür ise `SafeInt` sınıfı çağrıları [static_assert](../cpp/static-assert.md) geçersiz bir giriş parametresi belirtmek için.  
  
 Şablon türü kullanmak oluşturucular `U` giriş parametresi tarafından belirtilen türe otomatik olarak dönüştürmek `T`. `SafeInt` Sınıfı ve veri kaybı olmadan veri dönüştürür. Hata işleyicisine raporları `E` yazmak için veri dönüştüremezse `T` veri kaybı olmadan.  
  
 Oluşturursanız, bir `SafeInt` bir Boolean parametresinden değeri hemen başlatmak için gerekir. Oluşturamaz bir `SafeInt` kod kullanarak `SafeInt<bool> sb;`. Bu derleme hatası oluşturur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SafeInt Kitaplığı](../windows/safeint-library.md)   
 [SafeInt sınıfı](../windows/safeint-class.md)   
 [SafeIntException Sınıfı](../windows/safeintexception-class.md)