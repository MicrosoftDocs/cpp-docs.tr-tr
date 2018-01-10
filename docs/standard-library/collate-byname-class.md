---
title: "collate_byname sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: locale/std::collate_byname
dev_langs: C++
helpviewer_keywords: collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03a043e26aabde7e985c53dd33900f2ca1926487
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="collatebyname-class"></a>collate_byname Sınıfı
Dize sıralama kurallarıyla ilgili kültürel bir alana özgü bilgilerin alınmasını sağlayan, verili yerel ayarın bir harmanlama modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Locname`  
 Adlandırılmış bir yerel ayar.  
  
 `_Refs`  
 Bir başlangıç başvuru sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı olarak hizmet verebilir bir nesneyi tanımlayan bir [yerel model](../standard-library/locale-class.md#facet_class) türü [collate](../standard-library/collate-class.md#collate)\<CharType >. Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel ayar `_Locname`. Her oluşturucu temel nesnesiyle başlatır [collate](../standard-library/collate-class.md#collate)\<CharType > ( `_Refs`).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



