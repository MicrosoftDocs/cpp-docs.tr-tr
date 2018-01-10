---
title: "mem_fun1_t sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::mem_fun1_t
dev_langs: C++
helpviewer_keywords: mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db6449ad7cb350eddaa0abeecd9463fc53407d4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memfun1t-class"></a>mem_fun1_t Sınıfı
Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir işaretçi bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken üye işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;

 };
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Pm`  
 Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.  
  
 `_Pleft`  
 Nesne, `_Pm` üye işlevi çağrılır.  
  
 `right`  
 İçin belirtilen bağımsız değişken `_Pm`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Uyarlanabilir bir ikili işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı, bir kopyasını depolar `_Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( **_Pleft** -> \* `_Pm`) ( **sağ**).  
  
## <a name="example"></a>Örnek  
  Oluşturucusunun `mem_fun1_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye fonksiyonu bağdaştırıcıları kullanma örneği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



