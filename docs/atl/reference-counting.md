---
title: Başvuru sayım (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: f77939c25de19d619d6b4eeb2d3d6a0f3f1e5178
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473118"
---
# <a name="reference-counting"></a>Başvuru sayımı

COM kendisi, nesnenin artık kullanılıp kullanılmadığını düşündüğünde nesneyi bellekten kaldırmak otomatik olarak denemez. Bunun yerine, nesne Programcı kullanılmayan nesne kaldırmanız gerekir. Programcı, nesnenin başvuru sayısının göre kaldırılıp kaldırılamayacağını belirler.

COM kullanan `IUnknown` yöntemleri [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) ve [yayın](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), arabirimleri bir nesnede başvuru sayısını yönetme. Bu yöntemleri çağırmak için genel kurallar şunlardır:

- Her bir istemci bir arabirim işaretçisini aldığında `AddRef` arabiriminde çağrılmalıdır.

- Arabirim işaretçisi kullanılarak istemci bitirdi her çağırmalıdır `Release`.

Basit bir uygulamada her `AddRef` artırır ve her çağrı `Release` nesnesinin içindeki bir sayaç değişkeni azaltır çağırın. Sayısı sıfıra döndürüldüğünde arabirimi artık tüm kullanıcıları içeren ve kendisini bellekten kaldırmak ücretsizdir.

Böylece her nesneye (değil tek bir arabirim) başvuru sayılan başvuru sayımı de uygulanabilir. Bu durumda, her `AddRef` ve `Release` temsilciler merkezi bir uygulamaya nesne üzerinde arama ve `Release` , başvuru sayısı sıfır ulaştığında tüm nesneyi serbest bırakır.

> [!NOTE]
>  Olduğunda bir `CComObject`-türetilmiş nesnesi kullanılarak oluşturulduğunda **yeni** işleci, başvuru sayısı: 0. Bu nedenle, bir çağrı `AddRef` başarıyla oluşturduktan sonra yapılması gerektiğini `CComObject`-türetilmiş bir nesneye.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Başvuru sayımı yoluyla, nesne kullanım ömrü Yönetimi](/windows/desktop/com/managing-object-lifetimes-through-reference-counting)

