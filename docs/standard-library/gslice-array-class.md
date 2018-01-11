---
title: "gslice_array sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: valarray/std::gslice_array
dev_langs: C++
helpviewer_keywords: gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c030885dd0ab6b9c102167e9702dce02589973b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gslicearray-class"></a>gslice_array Sınıfı
Bir valarray genel dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak genel dilim nesneleri destekleyen bir yardımcı, iç Şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Type>  
class gslice_array : public gsplice {  
public:  
    typedef Type value_type;  
    void operator=(const valarray<Type>& x) const;

 
 
    void operator=(const Type& x) const;

 
 
    void operator*=(const valarray<Type>& x) const;

 
 
    void operator/=(const valarray<Type>& x) const;

 
 
    void operator%=(const valarray<Type>& x) const;

 
 
    void operator+=(const valarray<Type>& x) const;

 
 
    void operator-=(const valarray<Type>& x) const;

 
 
    void operator^=(const valarray<Type>& x) const;

 
 
    void operator&=(const valarray<Type>& x) const;

 
 
    void operator|=(const valarray<Type>& x) const;

 
 
    void operator<<=(const valarray<Type>& x) const;

 
 
    void operator>>=(const valarray<Type>& x) const;

 
 
// The rest is private or implementation defined  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf bir nesneye başvuru depolayan bir nesne tanımlar **va** sınıfının [valarray](../standard-library/valarray-class.md)**\<türü >**, bir nesne ile birlikte **gs**  sınıfının [gslice](../standard-library/gslice-class.md) aralarından seçim yapabileceğiniz öğe dizisi açıklayan **valarray\<türü >** nesnesi.  
  
 Oluşturmak bir **gslice_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne [va &#91; gs &#93;](../standard-library/valarray-class.md#op_at). Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı gslice_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında.  
  
 Şablon sınıfı belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve doğrudan programında kullanılamaz. Bir iç yardımcı Şablon sınıfı, bunun yerine dilim alt simge işleci tarafından kullanılır:  
  
 `gslice_array`\<**Türü** >  `valarray` \< **türü**>:: `operator[]` ( **constgslice &**).  
  
 Oluşturmak bir **gslice_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne **va [gsl]**, bir dilim için **gsl** valarray,  **Va**. Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı gslice_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında. Gslice_array tarafından denetlenen dizisi dilim oluşturucusu, her dilimi ve her dilim öğeleri arasındaki uzaklığı öğe sayısı ilk dilim ilk öğe dizini üç parametre tarafından tanımlanır.  
  
 Aşağıdaki örnekte:  
  
```  
const size_t lv[] = {2, 3};  
const size_t dv[] = {7, 2};  
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with  
//   indices 3, 5, 7, 10, 12, 14  
```  
  
 Dizinler yordamın geçerli olması geçerli olmalıdır.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [gslice::gslice](../standard-library/gslice-class.md#gslice) bildirme ve bir slice_array kullanma konusunda bir örnek.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<valarray >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

