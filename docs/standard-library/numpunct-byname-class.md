---
title: "numpunct_byname sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocnum/std::numpunct_byname
dev_langs: C++
helpviewer_keywords: numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84f71302d43a983772890611e55c56af9b21e922
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="numpunctbyname-class"></a>numpunct_byname Sınıfı
Türetilen Şablon sınıfı olarak hizmet verebilir bir nesneyi tanımlayan bir `numpunct` biçimlendirme ve noktalama sayısal ve Boole ifadelerin etkinleştirme belirli bir yerel ayar modeli.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

 };
```  
  
## <a name="remarks"></a>Açıklamalar  
 Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel ayar `_Locname`. Oluşturucu temel nesnesiyle başlatır [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType > ( `_Refs`).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



