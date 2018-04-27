---
title: slice_array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- valarray/std::slice_array
dev_langs:
- C++
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db8eb8018bac0d26efd6a9cdd397b07301fc4052
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="slicearray-class"></a>slice_array Sınıfı

Bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak dilim nesneleri destekleyen bir iç, yardımcı şablonu sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class slice_array : public slice {
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

Sınıfın bir nesnesi başvuruyu depolayan bir nesne sınıfı tanımlar [valarray](../standard-library/valarray-class.md)**\<türü >**, sınıfın bir nesnesi birlikte [dilim](../standard-library/slice-class.md), hangi aralarından seçim yapabileceğiniz öğe dizisi açıklar **valarray\<türü >** nesnesi.

Şablon sınıfı belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve doğrudan programında kullanılamaz. Dilim alt simge işleci tarafından kullanılan bir yardımcı, iç Şablon sınıfı:

`slice_array`\< **Tür**> `valarray`< **türü**:: `operator[]` ( `slice`).

Oluşturmak bir **slice_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at), bir dilim için **sl** valarray, **va**. Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı slice_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında. Slice_array tarafından denetlenen dizisi dilim oluşturucusu, dilim, öğe sayısını ve öğeleri arasındaki uzaklığı ilk öğe dizini üç parametre tarafından tanımlanır. Bir slice_array Kes valarray **va** tarafından bildirilen **va**[ `slice`(2, 5, 3)] dizinlerini 2, 5, 8, 11 ve 14'öğeleriyle seçer **va**. Dizinler yordamın geçerli olması geçerli olmalıdır.

## <a name="example"></a>Örnek

Örneğin bkz [slice::slice](../standard-library/slice-class.md#slice) bildirme ve bir slice_array kullanma konusunda bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
