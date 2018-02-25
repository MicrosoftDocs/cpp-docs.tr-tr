---
title: "Bağımsız değişkenler olmadan kendi Manipülatörlerinizi yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: abd4084a7ba4b011d95258867646fac20b5c6572
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma
Bağımsız değişkenler kullanmayın manipülatörlerinizi yazma sınıf türetme ne karmaşık makroları kullanımını gerektirir. Yazıcı çifti gerektirir varsayalım \<ESC > [Kalın modu girmek için tıklatın. Akışa doğrudan bu çifti ekleyebilirsiniz:  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 Veya tanımlayabilirsiniz `bold` karakterleri ekler manipulator:  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 Genel olarak tanımlanan `bold` işlev sürer bir `ostream` başvuru bağımsız değişkeni ve döndürür `ostream` başvuru. Tüm özel sınıfı öğelere erişim gerekmediği için üye işlevi veya bir arkadaş değil. `bold` İşlevi bağlayan akışa çünkü akışın `<<` işleci aşırı yüklenmiş işlevi, bu tür kabul etmek için şuna benzer bir bildirimi kullanarak:  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 Diğer aşırı yüklenmiş işleçler genişletmek için bu özelliği kullanın. Bu durumda, arızi olduğundan, `bold` akışa karakter ekler. Bitişik karakter yazdırıldığında bu akışa mutlaka eklendiğinde, işlev çağrılır. Bu nedenle, yazdırma akışın arabelleğe alma nedeniyle Gecikmeli.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış Akışları](../standard-library/output-streams.md)

