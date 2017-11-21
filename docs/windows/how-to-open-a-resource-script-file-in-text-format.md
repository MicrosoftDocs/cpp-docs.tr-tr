---
title: "Nasıl yapılır: kaynak betik dosyasını metin biçiminde açma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.resource
dev_langs: C++
helpviewer_keywords:
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19f6a105b255fd5ab4ecb777cc52cccf7a978b7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>Nasıl Yapılır: Kaynak Betik Dosyasını Metin Biçiminde Açma
Belirli kaynak Düzenleyicisi içindeki bir iletişim kutusu gibi bir kaynak açmadan projenizin kaynak komut dosyası (.rc) dosyasının içeriğini görüntülemek istediğiniz zaman zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasında tüm iletişim kutularını arasında bir dize aramak isteyebilirsiniz.  
  
> [!NOTE]
>  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
 Metin biçimindeki içerdiği tüm kaynaklar görüntülemek ve tarafından desteklenen genel işlemleri gerçekleştirmek için kaynak dosyası kolayca açabilirsiniz [metin düzenleyici](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1).  
  
> [!NOTE]
>  Kaynak düzenleyicileri .rc veya resource.h dosyaları doğrudan okuyamadı. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derler. Bu dosyayı bir derleme adımdır ve yalnızca simgesel verileri depolar. İşlem ile normal bir derleme gibi bilgileri (örneğin, Yorumlar) sembolik değil derleme işlemi sırasında göz ardı edilir. .Aps dosya .rc dosyasıyla out eşitlenmiş alır her .rc dosyasını yeniden oluşturur (kaydettiğinizde, örneğin, Kaynak Düzenleyici .rc dosyası ve resource.h dosyası geçersiz kılar). Kaynaklardaki değişiklikleri .rc dosyasında eklenen kalır ancak .rc dosyanın üzerine sonra açıklamaları her zaman kaybolur. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).  
  
### <a name="to-open-a-resource-script-file-as-text"></a>Kaynak betik dosyasını metin olarak açmak için  
  
1.  Gelen **dosya** menüsünü seçin **açık**, ardından **dosya.**  
  
2.  İçinde **Dosya Aç** iletişim kutusunda, metin biçiminde görüntülemek istediğiniz kaynak betik dosyasına gidin.  
  
3.  Dosyayı vurgulayın, ardından aşağı açılan oku tıklatın **açık** düğmesini (düğme sağ tarafta bulunur).  
  
4.  Seçin **birlikte Aç** açılır menüsünden.  
  
5.  İçinde **birlikte Aç** iletişim kutusu, tıklatın **kaynak kodu (metin) Düzenleyicisi**.  
  
6.  Gelen **açık olarak** aşağı açılan listesinden, **metin**.  
  
     Kaynak, kaynak kodu Düzenleyicisi'nde açar.  
  
 \-veya -  
  
1.  İçinde **Çözüm Gezgini**, .rc dosyasını sağ tıklatın.  
  
2.  Kısayol menüsünden **birlikte Aç...** seçeneğini belirleyip **kaynak kodu (metin) Düzenleyicisi**.  
  

  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak düzenleyicileri](../windows/resource-editors.md)