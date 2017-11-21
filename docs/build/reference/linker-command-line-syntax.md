---
title: "Bağlayıcı komut satırı sözdizimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 905ef180c2212e2efd708bb795162627b60ced79
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-command-line-syntax"></a>Bağlayıcı Komut Satırı Sözdizimi
BAĞLANTI çalıştırmak için. EXE, aşağıdaki komut söz dizimini kullanın:  
  
```  
LINK arguments  
```  
  
 `arguments` Seçenekleri ve dosya adları içerir ve herhangi bir sırada belirtilebilir. Seçenekler şunlardır: işlenen ilk sonra da dosyaları. Bağımsız değişkenler ayırmak için bir veya daha fazla boşluk ya da sekme kullanın.  
  
> [!NOTE]
>  Bu araç yalnızca başlatabilirsiniz [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] komut istemi. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor.  
  
 Komut satırında bir seçenek bir seçenek belirticisi oluşan bir tire (-) veya eğik çizgi (/) ve ardından seçeneği adına göre. Seçenek adları kısaltılmış olamaz. Bazı seçenekler iki nokta (:) sonra belirtilen bir bağımsız değişken alın. Hiçbir boşluk ya da sekme bir seçenek belirtimi içinde dışında/Comment seçeneğinde tırnak içine alınmış dize içinde izin verilir. Sayısal bağımsız ondalık veya dil C gösterimi belirtin. Seçenek adlarının ve kendi anahtar sözcüğü ya da dosya bağımsız değişkenler büyük küçük harfe duyarlı değildir, ancak bağımsız değişken olarak büyük küçük harfe duyarlı tanımlayıcılardır.  
  
 Bağlayıcı için bir dosya geçirmek için bağlantı komutundan sonra komut satırında dosya adını belirtin. Mutlak veya göreli bir yol adıyla belirtebilirsiniz ve dosya adını joker karakterleri kullanabilirsiniz. Nokta (.) ve dosya adı uzantısı atlarsanız, bağlantı dosyasının bulma amacıyla .obj varsayar. BAĞLANTI olmaması veya dosya adı uzantıları dosyaları içeriği hakkında varsayımlarda için kullanmaz; Dosya türü, inceleyerek belirler ve buna göre işler.  
  
 Link.exe (hata) başarı için sıfır değerini döndürür.  Aksi takdirde bağlayıcı bağlantıya durdurulmuş hata sayısını döndürür.  Örneğin, bağlayıcı LNK1104 oluşturursa, bağlayıcı 1104 döndürür.  Buna uygun olarak, bağlayıcı tarafından bir hata döndürdü en düşük hata numarasına 1000'dir.  128 dönüş değeri, işletim sistemi veya .config dosyası bir yapılandırma sorunu temsil eder; Yükleyici link.exe veya c2.dll yüklenmeyen.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)