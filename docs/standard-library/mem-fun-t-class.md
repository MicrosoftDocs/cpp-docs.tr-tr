---
title: "mem_fun_t sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::mem_fun_t
dev_langs: C++
helpviewer_keywords: mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d78a39fb29ac983c69bf792c4d567c850e697c53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memfunt-class"></a>mem_fun_t Sınıfı
Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir işaretçi bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan üye işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

 };
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Pm`  
 Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.  
  
 `_Pleft`  
 Nesne, `_Pm` üye işlevi çağrılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir uyarlanabilir birli işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı, bir kopyasını depolar `_Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( `_Pleft` ->*  `_Pm`) ().  
  
## <a name="example"></a>Örnek  
 Oluşturucusunun `mem_fun_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye fonksiyonu bağdaştırıcıları kullanma örneği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<işlev >](../standard-library/functional.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



