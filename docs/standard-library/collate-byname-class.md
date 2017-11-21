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
ms.openlocfilehash: 317160860374678f35b8ea7e883db7afe45fdf38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



