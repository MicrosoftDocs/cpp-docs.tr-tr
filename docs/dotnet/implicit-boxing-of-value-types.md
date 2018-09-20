---
title: Değer türlerini örtük kutulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e9c232dba6d766d0855bb4bb29e33d85b5fd5a2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387594"
---
# <a name="implicit-boxing-of-value-types"></a>Değer Türlerini Örtük Olarak Kutulama

Değer türleri kutulama, Visual C++ için C++ için Yönetilen Uzantılar'dan değişti.

Dil tasarımında size felsefi bir konum özelliği ile pratik deneyim uyguladık uygulanan ve isteğe bağlı olarak, uygulamada bir hata oluştu. Benzetme özgün birden çok devralma dil tasarımını Stroustrup bir türetilen sınıf oluşturucusu içinde bir sanal temel sınıf alt nesne başlatılamadı ve bu nedenle herhangi bir sınıf sanal temel olarak hizmet veren gerekli dil verdi sınıfı, varsayılan bir oluşturucu tanımlamanız gerekir. Herhangi bir sonraki sanal türetme tarafından çağrılır, varsayılan oluşturucudur.

Bir sanal temel sınıf hiyerarşisi sorun, paylaşılan sanal alt nesnelerin başlatılması için sorumluluk ile sonraki her türetme kaydırır olmasıdır. Ben bir temel sınıf için tanımlarsanız, örneğin, bu arabellek kullanıcı tarafından belirtilen boyutu bir arabellek ayrılması hangi başlatma gerektiriyor bağımsız değişken olarak oluşturucuya geçirilebilir. Ben daha sonra sonraki iki sanal türetme sağlarsanız, onları çağıran `inputb` ve `outputb`, her temel sınıf oluşturucusu için belirli bir değer sağlar. Ne zaman elde ediyorum artık, bir `in_out` hem sınıf `inputb` ve `outputb`, bu değerler paylaşılan sanal temel sınıf alt nesneye hiçbiri sensibly değerlendirmek için izin verilebilir.

Bu nedenle, özgün dil tasarımında, üye başlatma listesi içinde bir sanal temel sınıfın türetilmiş sınıf oluşturucu açık başlatma Stroustrup izin verilmiyor. Bu sorun çözüldüğünde, ancak uygulamada başlatma sanal temel sınıfın doğrudan başlatılmasının mümkün olmadığı kanıtladılar. Keith nihcl, Ulusal sağlık Enstitüsü kimin uygulayan adlı SmallTalk koleksiyon kitaplığını ücretsiz sürümünü uygulanmış, daha esnek bir dil tasarımla gelmesini he 'D Stroustrup ikna içinde bir ilkeye ses oluştu.

Nesne yönelimli hiyerarşik tasarımı prensibi, türetilmiş bir sınıf kendisi yalnızca anında temel sınıflarını özel olmayan uygulamasıyla ilgili tutar. Sanal devralma için esnek başlatma tasarım desteklemek için bu ilkeyi ihlal Stroustrup gerekiyordu. Bir hiyerarşideki en çok türetilen sınıf gerçekleşir hiyerarşiye nasıl derin bakılmaksızın tüm sanal alt nesne başlatmayı sorumluluğunu varsayar. Örneğin, `inputb` ve `outputb` her ikisini de hemen kendi sanal temel sınıfı açıkça başlatmaktan sorumludurlar. Zaman `in_out` hem türetilen `inputb` ve `outputb`, `in_out` sanal temel sınıf bir kez başlatma kaldırıldı ve başlatma açık içinde yapılan sorumlu olur `inputb` ve `outputb` olduğu gizlendi.

Bu, gerekli dil geliştiriciler, ancak karmaşık semantiği, esnekliği sağlar. Biz durumu olmalı ve yalnızca bir arabirim belirtmek izin vermek için sanal bir temel sınıf kısıtlamak isterseniz bu yükünü komplikasyon hemen çıkartılır. C++ içinde önerilen tasarım deyimidir budur. CLR programlamada, arabirim türü ile bir ilke oluşturulur.

İşte bir basit kod örnek - ve bu durumda, açık kutulama gerekli değildir:

```
// Managed Extensions for C++ requires explicit __box operation
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };
Object* myObjArray __gc[] = {
   __box(26), __box(27), __box(28), __box(29), __box(30)
};

Console::WriteLine( "{0}\t{1}\t{2}", __box(0),
   __box(my1DIntArray->GetLowerBound(0)),
   __box(my1DIntArray->GetUpperBound(0)) );
```

Gördüğünüz gibi çok paketleme devam ediyor yoktur. Visual C++'ın altında değer türü örtük olarak kutulama:

```
// new syntax makes boxing implicit
array<int>^ my1DIntArray = {1,2,3,4,5};
array<Object^>^ myObjArray = {26,27,28,29,30};

Console::WriteLine( "{0}\t{1}\t{2}", 0,
   my1DIntArray->GetLowerBound( 0 ),
   my1DIntArray->GetUpperBound( 0 ) );
```

## <a name="see-also"></a>Ayrıca Bkz.

[Değer Türleri ve Davranışları (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Kutulama](../windows/boxing-cpp-component-extensions.md)