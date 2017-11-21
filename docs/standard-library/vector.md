---
title: "&lt;vektör&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <vector>
dev_langs: C++
helpviewer_keywords: vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2c1f1b0d9c3b7c5949166b0018bf1e6e6fcbd14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltvectorgt"></a>&lt;vektör&gt;
Kapsayıcı Şablon sınıfı vektör ve çeşitli destekleyici şablonları tanımlar.  
  
 `vector` Doğrusal bir sıra içinde belirli bir türde öğeleri düzenler bir kapsayıcıdır. Öğesini ve dinamik ekleme ve kaldırma işlemleri için ve serisinden hızlı rastgele erişim sağlar. `vector` Rasgele erişim performansı üst düzey olduğunda tercih edilen sıralı bir kapsayıcısıdır.  
  
 Sınıfı hakkında daha fazla bilgi için `vector`, bkz: [vector sınıfı](../standard-library/vector-class.md). Özelleştirme hakkında bilgi için `vector<bool>`, bkz: [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Parametreler  
 Tür  
 Şablon parametresi vektörü depolanan veri türü için.  
  
 Ayırıcısı  
 Bellek ayırma ve ayırmayı kaldırma sorumlu saklı ayırıcısı nesnesi için şablon parametresi.  
  
 `left`  
 Bir karşılaştırma işlemi ilk (soldaki) vektörü  
  
 `right`  
 Bir karşılaştırma işlemi ikinci (sağdaki) vektörü.  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleci! =](../standard-library/vector-operators.md#op_neq)|Testleri işlecinin sol tarafındaki vektör nesnesi sağ tarafında vektör nesnesine eşit değil.|  
|[operator <](../standard-library/vector-operators.md#op_lt)|Vektör nesnesi işlecinin sol tarafındaki sağ tarafında vektör nesnesi küçükse testleri.|  
|[işleci\<=](../standard-library/vector-operators.md#op_gt_eq)|Vektör işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında vektör nesnesi eşit veya daha az olur.|  
|[operator ==](../standard-library/vector-operators.md#op_eq_eq)|Vektör nesnesi işlecinin sol tarafındaki sağ tarafında vektör nesnesine eşitse testleri.|  
|[operator >](../standard-library/vector-operators.md#op_gt)|Testleri işlecinin sol tarafındaki vektör nesnesi sağ tarafında vektör nesnesi değerinden daha büyük.|  
|[operator > =](../standard-library/vector-operators.md#op_gt_eq)|Vektör işlecinin sol tarafındaki sağ tarafında vektör nesnesine eşit veya daha büyük bir nesneyse testleri.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[vector sınıfı](../standard-library/vector-class.md)|Doğrusal bir düzenleme içinde belirli bir türde öğelerini düzenlemek ve herhangi bir öğeye hızlı rastgele erişim izin veren dizisi kapsayıcıların bir şablon sınıfı.|  
  
### <a name="specializations"></a>Uzmanlıklar  
  
|||  
|-|-|  
|[vektör\<bool > sınıfı](../standard-library/vector-bool-class.md)|Şablon sınıfı vektör türündeki öğeler için tam uzmanlaşması `bool` uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcı ile.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<vektör >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

