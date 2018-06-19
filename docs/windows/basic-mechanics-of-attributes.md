---
title: Özniteliklerin temel Mekanikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6db2994a2606f6c4d0cb4cd581ec46d87ca3d2c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864947"
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