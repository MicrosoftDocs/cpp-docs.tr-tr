---
title: "codecvt_base sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3d1ae1c2bae5c4ce0ab4c7cb6ecadec194f5f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtbase-class"></a>codecvt_base Sınıfı
Bir numaralandırma türü tanımlamak için kullanılan codecvt sınıfı için bir taban sınıf denir **sonuç**, bir dönüştürme sonucu göstermek için model üye işlevleri için dönüş türü olarak kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfının tüm özelleştirmeleri için ortak bir numaralandırma sınıf tanımlar [codecvt](../standard-library/codecvt-class.md). Olası dönüş değerleri numaralandırması sonucu açıklanmaktadır [do_in](../standard-library/codecvt-class.md#do_in) veya [do_out](../standard-library/codecvt-class.md#do_out):  
  
- **Tamam** iç ve dış karakter kodlamaları arasında dönüştürme başarılı olursa.  
  
- **Kısmi** hedef dönüştürme işleminin başarılı olması için yeterince büyük değilse.  
  
- **hata** kaynak sırası hatalı olması durumunda oluşturulmuş.  
  
- **noconv** dönüştürme işlevi uyguluyorsa.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



