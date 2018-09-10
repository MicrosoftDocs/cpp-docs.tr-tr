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
- attributes [C++/CLI], inserting in code
- attributes [C++/CLI], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f6563d61988beb5df91ce0a3ccb871e3a5a9adc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315957"
---
# <a name="basic-mechanics-of-attributes"></a>Özniteliklerin Temel Mekanikleri

Öznitelikleri projenize eklemek için üç yolu vardır. İlk olarak, bunları el ile kaynak kodunuza ekleyebilirsiniz. İkinci olarak, projenizde bir nesnenin özellik kılavuzu kullanarak bunları ekleyebilirsiniz. Son olarak, bunları çeşitli sihirbazlar kullanarak ekleyebilirsiniz. Kullanma hakkında daha fazla bilgi için **özellikleri** penceresi ve çeşitli sihirbazlar [oluşturma ve yönetme, Visual C++ projeleri](../ide/creating-and-managing-visual-cpp-projects.md).

Proje derlenirken olarak önce derleyici bir nesne dosyası üretmek her C++ kaynak dosyası ayrıştırır. Ancak, derleyici bir öznitelik karşılaştığında, ayrıştırılır ve sözdizimsel olarak doğrulandı. Derleyici daha sonra kod ekleyin veya derleme zamanında başka değişiklikler yapmak için bir öznitelik sağlayıcısı dinamik olarak çağırır. Sağlayıcının uygulama özniteliği türüne bağlı olarak farklılık gösterir. Örneğin, ATL ilgili öznitelikleri Atlprov.dll tarafından uygulanır.

Aşağıdaki şekil, derleyici ve öznitelik sağlayıcısı arasındaki ilişki gösterilmektedir.

![Bileşen özniteliği iletişimini](../windows/media/vccompattrcomm.gif "vcCompAttrComm")

> [!NOTE]
> Öznitelik kullanımı, kaynak dosyasının içeriğini değiştirmez. Kodu oluşturulan özniteliği görünür olup yalnızca bir kez, hata ayıklama oturumları sırasında dir. Ayrıca, projedeki her kaynak dosyası için öznitelik değiştirme sonuçlarını görüntüleyen bir metin dosyası oluşturabilirsiniz. Bu yordamı hakkında daha fazla bilgi için bkz. [/Fx (eklenen kodu Birleştir)](../build/reference/fx-merge-injected-code.md) ve [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

Çoğu C++ yapılarına uygun kullanımlarını tanımlayan bir dizi özellikleri özniteliklere sahiptir. Bu öznitelik bağlamı olarak adlandırılır ve öznitelik bağlamı tablosunda her öznitelik başvuru konusu ele. Örneğin, [coclass'ı](../windows/coclass.md) özniteliği yalnızca uygulanabilir bir varolan bir sınıf veya yapı, başlangıcı yerine sonundan [cpp_quote](../windows/cpp-quote.md) C++ kaynak dosyası içinde istenen yere eklenebileceğini özniteliği.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../windows/attributed-programming-concepts.md)