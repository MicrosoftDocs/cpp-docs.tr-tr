---
title: "Bayt ve geniş akışlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Byte and Wide Streams
dev_langs: C++
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d09e110fd428b13e501647d97a0878df0e9392a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="byte-and-wide-streams"></a>Bayt ve Geniş Akışlar
Bir bayt akış dosya bir bayt dizisi değerlendirir. Programında, akış bayt aynı dizisidir.  
  
 Bunun aksine, geniş bir akış bir dosyası çok çeşitli kodlama kuralları olabilir genelleştirilmiş birden çok baytlı karakter dizisi değerlendirir. (Metin ve ikili dosyaları yine okunur ve daha önce açıklandığı şekilde yazılmış.) Programında, akış geniş karakterler karşılık gelen sırası gibi görünüyor. İki sunumu arasında dönüştürme standart C Kitaplığı içinde oluşur. Dönüştürme kuralları temelde için yapılan bir çağrı tarafından değiştirilebilir [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) kategori değiştirir `LC_CTYPE`. Geniş her akış dönüştürme kurallarını geniş yönlendirilmiş olur ve bu kuralları olsa bile korur anda belirler kategori `LC_CTYPE` sonradan değiştirir.  
  
 Geniş bir akış içinde konumlandırma metin steams için olduğu gibi aynı sınırlamalar düşer. Ayrıca, dosya konumu göstergesi durumu bağımlı kodlama ile mücadele etmek iyi olabilir. Genellikle, her iki bir bayt akış ve türünde bir nesne içinde uzaklığı içerir `mbstate_t`. Bu nedenle, geniş bir akış içinde dosya konumu elde etmek için yalnızca güvenilir çağırarak yoldur [fgetpos](../c-runtime-library/reference/fgetpos.md), ve bu şekilde elde bir konuma geri yüklemek için yalnızca güvenilir bir yolu çağırarak [fsetpos](../c-runtime-library/reference/fsetpos.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar ve akışlar](../c-runtime-library/files-and-streams.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)