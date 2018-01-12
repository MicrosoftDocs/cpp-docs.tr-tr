---
title: "atomic yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic/std::atomic
dev_langs: C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5525953e5f4ba68fdf1b84b02046d9ab4679abe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atomic-structure"></a>atomic Yapısı
Türünde bir saklı değeri atomik işlemler gerçekleştiren bir nesneyi tanımlayan `Ty`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[atomic](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|Atomik bir nesne oluşturur.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[atomic::operator Ty işleci](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|Okur ve saklanan değeri döndürür. ([atomic::load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[atomic::operator = işleci](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|Saklanan değeri değiştirmek için belirtilen değeri kullanır. ([atomic::store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[atomic::operator ++ işleci](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|Depolanan değer artırır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator += işleci](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|Belirtilen bir değeri saklı değerine ekler. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator--işleci](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|Azaltır depolanan değer. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator-= işleci](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|Saklanan değeri belirtilen değeri çıkarır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator & = işleci](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|Bit tabanlı gerçekleştirir `and` belirtilen değere ve depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator &#124; = işleci](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|Bit tabanlı gerçekleştirir `or` belirtilen değere ve depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|  
|[atomic::operator ^ = işleci](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|Bit tabanlı gerçekleştirir `exclusive or` belirtilen değere ve depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[compare_exchange_strong](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|Gerçekleştiren bir `atomic_compare_and_exchange` işlemi `this` ve sonucu döndürür.|  
|[compare_exchange_weak](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|Gerçekleştiren bir `weak_atomic_compare_and_exchange` işlemi `this` ve sonucu döndürür.|  
|[fetch_add](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|Belirtilen bir değeri saklı değerine ekler.|  
|[fetch_and](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|Bit tabanlı gerçekleştirir `and` belirtilen değere ve depolanan değer.|  
|[fetch_or](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|Bit tabanlı gerçekleştirir `or` belirtilen değere ve depolanan değer.|  
|[fetch_sub](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|Saklanan değeri belirtilen değeri çıkarır.|  
|[fetch_xor](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|Bit tabanlı gerçekleştirir `exclusive or` belirtilen değere ve depolanan değer.|  
|[is_lock_free](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|Belirtir olup olmadığını atomik işlemleri `this` olan *kilidi serbest*. Atomik bir tür olduğundan *kilidi serbest* ilgili türdeki atomik bir işlem kilitleri kullanıyorsanız.|  
|[Yükleme](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|Okur ve saklanan değeri döndürür.|  
|[Depolama](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|Saklanan değeri değiştirmek için belirtilen değeri kullanır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türü `Ty` olmalıdır *trivially copyable*. Diğer bir deyişle, kullanarak [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) kendi bayt kopyalamak için geçerli bir üretmek gerekir `Ty` özgün nesne eşit karşılaştırır nesnesi. `compare_exchange_weak` Ve `compare_exchange_strong` üye işlevlerini kullanmak [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) iki olup olmadığını belirlemek için `Ty` değerleri eşit. Bu işlevler kullanmaz bir `Ty`-tanımlı `operator==`. Üye işlevlerini `atomic` kullanmak `memcpy` türü değerleri kopyalamak için `Ty`.  
  
 Kısmi uzmanlığı `atomic<Ty *>`, tüm işaretçi türleri için bulunmaktadır. Yönetilen işaretçi değeri bir uzaklık eklenmesi veya bir uzaklığı çıkarma uzmanlık etkinleştirir. Aritmetik işlemler türünde bir bağımsız değişken Al `ptrdiff_t` ve boyutuna göre bu bağımsız değişken Ayarla `Ty` aritmetik sıradan adresi ile tutarlı olacak şekilde.  
  
 Dışında tam sayı her türü için bir uzmanlık var. `bool`. Her uzmanlık zengin bir atomik aritmetik ve mantıksal işlemleri için yöntemleri sağlar.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Tam sayı özelleştirmeleri karşılık gelen öğesinden türetilen `atomic_integral` türleri. Örneğin, `atomic<unsigned int>` türetildiği `atomic_uint`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<atomik >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<atomik >](../standard-library/atomic.md)   
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)



