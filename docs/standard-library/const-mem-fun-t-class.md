---
title: const_mem_fun_t Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b805bf5f6bf39209e56a0b19008db913202cedf2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="constmemfunt-class"></a>const_mem_fun_t Sınıfı
Bir başvuru bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>  
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
 };
```  
  
#### <a name="parameters"></a>Parametreler  
 `Pm`  
 Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.  
  
 `Pleft`  
 Nesne, `Pm` üye işlevi çağrılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir uyarlanabilir birli işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı, bir kopyasını depolar `Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( `Pleft` -> \* `Pm`) () **const**.  
  
## <a name="example"></a>Örnek  
 Oluşturucusunun `const_mem_fun_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye fonksiyonu bağdaştırıcıları kullanma örneği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



