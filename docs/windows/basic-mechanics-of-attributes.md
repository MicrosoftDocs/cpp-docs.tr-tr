---
title: "Özniteliklerin temel Mekanikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebf81d5bfb20f151cc8f405fb8346b66451f77e2
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="basic-mechanics-of-attributes"></a>Özniteliklerin Temel Mekanikleri
Öznitelikleri projenize eklemek için üç yolu vardır. İlk olarak, bunları el ile kaynak kodunuza ekleyebilirsiniz. İkinci olarak, bir nesnenin özellik Kılavuzu projenizde kullanarak bunları ekleyebilirsiniz. Son olarak, çeşitli sihirbazları kullanarak bunları ekleyebilirsiniz. Özellikler penceresini ve çeşitli sihirbazları kullanarak daha fazla bilgi için bkz: [oluşturma ve yönetme Visual C++ projeleri](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Proje yapılandırıldığında olarak daha önce derleyici bir nesne dosyası üretmeyi her C++ kaynak dosyasının ayrıştırır. Ancak, derleyici bir öznitelik karşılaştığında, bu ayrıştırılmış ve sözdizimsel olarak doğrulandı. Derleyici dinamik olarak kod ekleme veya derleme zamanında başka değişiklikler yapmak için bir öznitelik sağlayıcısı sonra çağırır. Sağlayıcı uygulaması özniteliği türüne bağlı olarak değişir. Örneğin, ATL ilgili öznitelikleri Atlprov.dll tarafından uygulanır.  
  
 Aşağıdaki şekilde derleyici ve öznitelik sağlayıcısı arasındaki ilişki gösterilmektedir.  
  
 ![Bileşen özniteliği iletişimini](../windows/media/vccompattrcomm.gif "vcCompAttrComm")  
  
> [!NOTE]
>  Öznitelik kullanımı kaynak dosyasının içeriğini değiştirmez. Hata ayıklama oturumları sırasında oluşturulan öznitelik kodu görünür yalnızca bir kez gösterilecektir. Ayrıca, projesinde her kaynak dosyası için öznitelik değiştirme sonuçlarını görüntüleyen bir metin dosyası oluşturabilirsiniz. Bu yordam hakkında daha fazla bilgi için bkz: [/Fx (eklenen kodu Birleştir)](../build/reference/fx-merge-injected-code.md) ve [eklenen kod hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).  
  
 Çoğu C++ yapıları gibi öznitelikleri doğru kullanımı tanımlayan bir dizi özelliklere sahip. Bu öznitelik bağlamı olarak adlandırılır ve her özniteliği başvuru konusu için öznitelik bağlam tablosunda ele. Örneğin, [coclass](../windows/coclass.md) özniteliği yalnızca uygulanabilir bir varolan sınıf veya yapı, tersine [cpp_quote](../windows/cpp-quote.md) bir C++ kaynak dosyası içindeki herhangi bir yere eklenebilir özniteliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../windows/attributed-programming-concepts.md)