---
title: Başvuru sayım (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9288eda15b0bac3d3694ee56a2f427aefb60e032
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086440"
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

