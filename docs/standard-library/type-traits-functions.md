---
title: "&lt;type_traits&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: 67fd80381854bd141fd47314544aca745f9a9aaf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt; işlevleri
||||  
|-|-|-|  
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|  
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|  
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|  
|[is_trivially_move_constructible](#is_trivially_move_constructible)|  
  
##  <a name="is_assignable"></a>  is_assignable  
 Bir değeri olup olmadığını sınar `From` türü atanabilen bir `To` türü.  
  
```  
template <class To, class From>  
struct is_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 Bitiş  
 Atamayı alan nesnesi türü.  
  
 Başlangıç  
 Değer sağlayan nesne türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
##  <a name="is_copy_assignable"></a>  is_copy_assignable  
 Türüne sahip olup olmadığını test atamada kopyalanabilir.  
  
```  
template <class Ty>  
struct is_copy_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir kopya atama işleci, aksi takdirde sahip bir sınıftır. İs_assignable eşdeğer\<Ty &, const Ty & >.  
  
##  <a name="is_copy_constructible"></a>  is_copy_constructible  
 Kopya Oluşturucu türündeyse testleri.  
  
```  
template <class Ty>  
struct is_copy_constructible;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu kopya Oluşturucu, aksi takdirde sahip bir sınıftır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
struct Copyable  
{  
    int val;  
};  
  
struct NotCopyable  
{  
   NotCopyable(const NotCopyable&) = delete;  
   int val;  
  
};  
  
int main()  
{  
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha  
        << std::is_copy_constructible<Copyable>::value << std::endl;  
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha  
        << std::is_copy_constructible<NotCopyable>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
```Output  
is_copy_constructible<Copyable> == true  
is_copy_constructible<NotCopyable > == false  
```  
  
##  <a name="is_default_constructible"></a>  is_default_constructible  
 Bir türü varsayılan bir oluşturucu varsa testleri.  
  
```  
template <class Ty>  
struct is_default_constructible;  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu varsayılan bir oluşturucu, aksi takdirde sahip bir sınıf türü. Bu koşulu eşdeğerdir `is_constructible<T>`. Tür `T` tam bir tür olmalıdır `void`, veya bilinmeyen bağlı bir dizi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
struct Simple  
{  
    Simple() : val(0) {}  
    int val;  
};  
  
struct Simple2  
{  
    Simple2(int v) : val(v) {}  
    int val;  
};  
  
int main()  
{  
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha  
        << std::is_default_constructible<Simple>::value << std::endl;  
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha  
        << std::is_default_constructible<Simple2>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
```Output  
is_default_constructible<Simple> == true  
is_default_constructible<Simple2> == false  
```  
  
##  <a name="is_move_assignable"></a>  is_move_assignable  
 Türü olabiliyorsa, testleri atanan taşıyın.  
  
```  
template <class T>  
struct is_move_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir türü taşıma atanabilir ise rvalue başvuru türüne bir başvuru türüne atanabilir. Türü koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri önerilebilir skaler türler ve taşıma atama işleçleri derleyicinin ürettiği veya kullanıcı tanımlı olan sınıf türünü taşıyın.  
  
##  <a name="is_move_constructible"></a>  is_move_constructible  
 Bir taşıma oluşturucusuna türüne sahip olup olmadığını sınar.  
  
```  
template <class T>  
struct is_move_constructible;  
```  
  
### <a name="parameters"></a>Parametreler  
 T  
 Değerlendirilecek türü  
  
### <a name="remarks"></a>Açıklamalar  
 Türü ise true olarak değerlendirilir türü koşulu `T` bir taşıma işlemi kullanılarak oluşturulabilir. Bu koşul eşdeğerdir `is_constructible<T, T&&>`.  
  
##  <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable  
 Türüne sahip olup olmadığını sınar bir **nothrow** atama işleci taşıyın.  
  
```  
template <class Ty>  
struct is_nothrow_move_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir nothrow taşıma atama işleci, aksi takdirde sahiptir.  
  
##  <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable  
 Türü bir önemsiz copy atama işleci olup olmadığını sınar.  
  
```  
template <class Ty>  
struct is_trivially_copy_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu bir önemsiz copy atama işleci, aksi takdirde sahip bir sınıftır.  
  
 Bir sınıf için bir atama Oluşturucusu `T` , örtük olarak sağlanır, sınıf deyimle `T` sınıfı hiçbir sanal işleve sahip `T` hiçbir sanal temellerine sahip, sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz sahip atama işleçleri ve sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz atama işleçleri sahiptir.  
  
##  <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable  
 Önemsiz taşıma atama işleci türüne sahip olup olmadığını sınar.  
  
```  
template <class Ty>  
struct is_trivially_move_assignable;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma atama işleci, aksi takdirde sahip bir sınıftır.  
  
 Bir sınıf için bir taşıma atama işleci `Ty` deyimle varsa:  
  
 örtük olarak sağlanır  
  
 sınıf `Ty` hiçbir sanal işleve sahip  
  
 sınıf `Ty` hiçbir sanal temellerine sahip  
  
 sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip  
  
 sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma atama işleçleri sahip  
  
##  <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible  
 Önemsiz türündeyse testleri Oluşturucusu taşıyın.  
  
```  
template <class Ty>  
struct is_trivially_move_constructible;  
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz taşıma oluşturucusu, aksi durumda olan bir sınıftır.  
  
 Bir sınıf için bir taşıma oluşturucusuna `Ty` deyimle varsa:  
  
 örtülü olarak bildirilen  
  
 parametre türleri örtük bir bildirimi gereksinimlerine eşdeğer  
  
 sınıf `Ty` hiçbir sanal işleve sahip  
  
 sınıf `Ty` hiçbir sanal temellerine sahip  
  
 sınıfta hiç geçici olmayan statik veri üyeleri yok  
  
 tüm doğrudan taban sınıfının `Ty` Önemsiz taşıma oluşturucuları sahip  
  
 sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip  
  
 sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz taşıma oluşturucuları sahip  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)

