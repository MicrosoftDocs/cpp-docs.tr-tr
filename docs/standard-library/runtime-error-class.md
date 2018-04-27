---
title: runtime_error sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- stdexcept/std::runtime_error
dev_langs:
- C++
helpviewer_keywords:
- runtime_error class
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98f10354af9acf642feccee26ef71a436f0a5619
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="runtimeerror-class"></a>runtime_error Sınıfı

Sınıfı yalnızca program yürüttüğünde hatalarını raporlamak için büyük olasılıkla algılanabilir oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
class runtime_error : public exception {
public:
    explicit runtime_error(const string& message);

    explicit runtime_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer [özel durum sınıfı](../standard-library/exception-class.md) bir kopyası **ileti**`.`[veri](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Örnek

```cpp
// runtime_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
// runtime_error
   try
   {
      locale loc( "test" );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
\* Output:
Caught bad locale name
Type class std::runtime_error
*\
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<stdexcept >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
