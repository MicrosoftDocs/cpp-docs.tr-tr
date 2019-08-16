---
title: Başvuru sayımı (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 565b74956280d4e80c41376ead4249e69980a80e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492229"
---
# <a name="reference-counting"></a>Başvuru sayımı

COM 'un kendisi, nesnenin artık kullanılmıyor olduğunu düşündüğü zaman bir nesneyi bellekten kaldırmayı otomatik olarak denemez. Bunun yerine, nesne programlayıcı kullanılmamış nesneyi kaldırmalıdır. Programcı, bir nesnenin bir başvuru sayısına göre kaldırılıp kaldırılamayacağını belirler.

COM, bir `IUnknown` nesnedeki arabirimlerin başvuru sayısını yönetmek için, [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)yöntemlerini kullanır. Bu yöntemleri çağırmak için genel kurallar şunlardır:

- Bir istemci bir arabirim işaretçisi `AddRef` aldığında arabirim üzerinde çağrılmalıdır.

- İstemci, arabirim işaretçisini kullanmayı bitirdiğinde, çağrısı `Release`gerekir.

Basit bir uygulamada her `AddRef` bir çağrı artar ve her `Release` bir çağrı nesnenin içindeki bir sayaç değişkenini azaltır. Sayı sıfıra döndüğünde, arabirimin artık kullanıcıları yoktur ve kendisini bellekten kaldırmak ücretsizdir.

Başvuru sayımı, nesneye yapılan her başvurunun (tek bir arabirime değil) sayılmasını sağlamak için de uygulanabilir. Bu durumda, her `AddRef` ve `Release` çağrısı nesnesi üzerinde merkezi bir uygulamaya temsilci atar ve `Release` başvuru sayısı sıfıra ulaştığında tüm nesneyi serbest bırakır.

> [!NOTE]
>  Türetilmiş bir `CComObject`nesne **New** işleci kullanılarak oluşturulduğunda, başvuru sayısı 0 ' dır. Bu nedenle, `CComObject`ile türetilmiş `AddRef` nesne başarıyla oluşturulduktan sonra bir çağrısı yapılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Başvuru sayımı aracılığıyla nesne ömrünü yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
