---
title: "Nasıl yapılır: (tek başına) proje dışındaki kaynak betik dosyasını açma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- .rc files, viewing resources
- resource script files, viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2dd3bb3996fca1fd2c73ff98e7f391d27911ad15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-project-standalone"></a>Nasıl Yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)
Açık bir projeniz gerek kalmadan, kaynakları .rc dosyasında görüntüleyebilirsiniz. .Rc dosya açılırken içinde aksine belge penceresinde açılır [kaynak görünümü](../windows/resource-view-window.md) penceresi (dosya projesi içinde açık olduğunda bu yaptığı gibi).  
  
> [!NOTE]
>  Bazı komutlar yalnızca dosyanın açılmış tek başına (dışında bir proje) olduğunda kullanılabilir olmadığından önemli bir fark budur. Dosyanın dışında bir proje açıldığında, örneğin, yalnızca bir dosyayı farklı bir biçimde veya farklı bir dosya adı olarak kaydedebilirsiniz ( **Kaydet** komutu, içinde bir proje bir dosya açıldığında kullanılamıyor).  
  
### <a name="to-open-an-rc-file-outside-a-project"></a>Proje dışındaki bir .rc dosyasını açmak için  
  
1.  Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.  
  
2.  İçinde **açık dosya** iletişim kutusunda, görüntülemek, dosyayı vurgulayın ve tıklatın istediğiniz kaynak betik dosyasına gidin **açık**.  
  
    > [!NOTE]
    >  Proje ilk açarsanız (**dosya**, **açmak**, **proje**), bazı komutlar için kullanılamaz. "Tek başına" dosya açılırken proje yüklemeden açmadan anlamına gelir.  
  
 Açın ve kaynak dosyasını metin biçiminde görüntülemek için bkz: [bir kaynak betik (.rc) dosya düzenleme](../windows/how-to-open-a-resource-script-file-in-text-format.md).  
  
#### <a name="to-open-multiple-rc-files-outside-a-project"></a>Proje dışındaki birden çok .rc dosyaları açmak için  
  
1.  Tek başına hem de kaynak dosyalarını açın. Örneğin, Source1.rc ve Source2.rc açın.  
  
    1.  Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.  
  
    2.  İçinde **Dosya Aç** iletişim kutusunda, istediğiniz (Source1.rc) açın, dosyayı vurgulayın ve ' ilk kaynak betik dosyasına gidin **açmak**.  
  
    3.  İkinci .rc dosyasını (Source2.rc) açmak için önceki adımı yineleyin.  
  
         .Rc dosyaları ayrı belgeler Windows'da artık açık.  
  
2.  Her iki .rc dosyaları açık olduğunda, aynı anda görüntüleyebilmeniz pencereleri döşe:  
  
    -   Gelen **penceresi** menüsünde seçin **yeni yatay sekme grubu** veya **yeni dikey sekme grubu**.  
  
         \-veya -  
  
    -   .Rc dosyaları birine sağ tıklayın ve seçin **yeni yatay sekme grubu** veya **yeni dikey sekme grubu** kısayol menüsünden.  
  
> [!NOTE]
>  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  

  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)