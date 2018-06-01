---
title: Özel derleme adımının veya derleme olayının çıktısını biçimlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7da71e6391d2d3223b47ba528686d2fec003ab3a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33321356"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Özel Derleme Adımının veya Derleme Olayının Çıktısını Biçimlendirme
Özel derleme adımının veya derleme olayının çıktısını doğru biçimlendirildiğinden, kullanıcılar aşağıdaki yararları alın:  
  
-   Uyarıları ve hataları sayılır **çıkış** penceresi.  
  
-   Çıktı görünür **görev listesi** penceresi.  
  
-   Çıktıda tıklayarak **çıkış** penceresi uygun konu görüntüler.  
  
-   F1 işlemleri de etkinleştirildiğinde **görev listesi** penceresi veya **çıkış** penceresi.  
  
 Çıkış biçimi şöyle olmalıdır:  
  
 {*filename* (*satır #* [, *sütun #*]) &#124; *toolname*} **:**  
  
 [*herhangi bir metin*] {**hata** &#124; **uyarı**} *kod ###***:*** yerelleştirilebilir dize*  
  
 [ *herhangi bir metin* ]  
  
 Konum:  
  
-   {*bir* &#124; *b*} bir ya da seçimdir *bir* veya *b*.  
  
-   [`ccc`] bir isteğe bağlı dize ya da parametre.  
  
 Örneğin:  
  
 C:\\*sourcefile.cpp*(134): hata C2143: sözdizimi hatası: eksik ';' önce '}'  
  
 BAĞLANTI: önemli hatası LNK1104: dosyayı açamıyor '*somelib.lib*'  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)