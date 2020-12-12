---
description: 'Daha fazla bilgi edinin: derleme olay özellikleri (Linux C++)'
title: Uzak derleme olayları (Linux C++)
ms.date: 06/07/2019
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
ms.openlocfilehash: f134a882202881b1b89230459cc21c1b9757f6db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169820"
---
# <a name="build-event-properties-linux-c"></a>Derleme olayı özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="pre-build-event"></a>Oluşturma öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma öncesi olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Oluşturma öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir söz dizimini kullanarak yerel-uzak eşleme çiftleri belirtebilirsiniz: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

## <a name="pre-link-event"></a>Bağlama öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Bağlama öncesi olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Bağlama öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir söz dizimini kullanarak yerel-uzak eşleme çiftleri belirtebilirsiniz: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

## <a name="post-build-event"></a>Oluşturma sonrası olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma sonrası olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Oluşturma sonrası olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir söz dizimini kullanarak yerel-uzak eşleme çiftleri belirtebilirsiniz: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

## <a name="remote-pre-build-event"></a>Uzaktan derleme öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma öncesi olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir. |
| Açıklama | Oluşturma öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, uzak bir dosyanın yerel makinede belirtilen konuma kopyalanabilmesi için şu şekilde bir sözdizimi kullanarak uzak-yerel eşleme çiftlerine belirtin: fullremotepath1: = fulllocalpath1; fullremotepath2: = fulllocalpath2. |

## <a name="remote-pre-link-event"></a>Uzak bağlama öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Bağlama öncesi olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir. |
| Açıklama | Bağlama öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, uzak bir dosyanın yerel makinede belirtilen konuma kopyalanabilmesi için şu şekilde bir sözdizimi kullanarak uzak-yerel eşleme çiftlerine belirtin: fullremotepath1: = fulllocalpath1; fullremotepath2: = fulllocalpath2. |

## <a name="remote-post-build-event"></a>Oluşturma sonrası uzak olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma sonrası olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir. |
| Açıklama | Oluşturma sonrası olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, uzak bir dosyanın yerel makinede belirtilen konuma kopyalanabilmesi için şu şekilde bir sözdizimi kullanarak uzak-yerel eşleme çiftlerine belirtin: fullremotepath1: = fulllocalpath1; fullremotepath2: = fulllocalpath2. |

::: moniker-end
