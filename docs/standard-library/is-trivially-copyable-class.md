---
title: "is_trivially_copyable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivially_copyable
dev_langs: C++
helpviewer_keywords: is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5cfb92693d0bc5d120e2c1bb46eceb4822fd0ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable sınıfı
Türü trivially copyable türü olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct is_trivially_copyable;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu trivially copyable, aksi takdirde türüdür. Trivially copyable türleri hiçbir Önemsiz olmayan kopyalama işlemleri, taşıma işlemler veya Yıkıcılar sahip. Genellikle, bir kopyalama işlemi Bitsel kopya olarak uygulanırsa, önemsiz kabul edilir. Yerleşik türler ve diziler trivially copyable türlerinin trivially copyable.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



