---
title: "money_base sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e00b5f385a38a116cae245d525afc11d48f56762
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="moneybase-class"></a>money_base Sınıfı
Bir numaralandırma ve Şablon sınıfı tüm özelleştirmeleri için ortak bir yapı sınıf tanımlar [moneypunct](../standard-library/moneypunct-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
```    
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};  
```  
## <a name="remarks"></a>Açıklamalar  
 Numaralandırma **bölümü** yapısı düzeninde dizi alanının öğelerinde olası değerleri açıklanmaktadır. Değerlerini **bölümü** şunlardır:  
  
- **Hiçbiri** sıfır veya daha fazla boşluk veya hiçbir şey oluşturmak üzere.  
  
- **oturum** eşleşen veya olumlu veya olumsuz bir oturum oluşturur.  
  
- **alan** sıfır veya daha fazla boşluk veya bir alan oluşturmak üzere.  
  
- **Sembol** veya bir para birimi simgesini oluşturmak üzere.  
  
- **değer** veya parasal bir değer üretmek üzere.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



