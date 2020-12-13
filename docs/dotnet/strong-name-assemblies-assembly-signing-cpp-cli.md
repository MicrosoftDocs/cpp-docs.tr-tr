---
description: 'Daha fazla bilgi edinin: tanımlayıcı ad derlemeleri (derleme Imzalama) (C++/CLı)'
title: Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: 9fc08df759fa384ed13dbe3d8c3eb2d843183517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335311"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)

Bu konuda, derlemenizi bir tanımlayıcı ad vermek olarak adlandırılan derlemenizi nasıl imzalayabileceğiniz anlatılmaktadır.

## <a name="remarks"></a>Açıklamalar

Visual C++ kullanırken, derleme imzalama için CLR öznitelikleriyle ilgili sorunları önlemek üzere derlemenizi imzalamak için bağlayıcı seçeneklerini kullanın:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Özniteliklerin kullanılmasıyla ilgili nedenler, anahtar adının derleme meta verilerinde görünür olması ve dosya adı gizli bilgiler içerdiğinde bir güvenlik riski olabilir. Ayrıca, bir derlemeye tanımlayıcı ad vermek için CLR özniteliklerini kullanırsanız ve sonra derleme üzerinde mt.exe gibi bir işlem sonrası aracı çalıştırmak için Visual C++ geliştirme ortamı tarafından kullanılan yapı işlemi derlemenin imzalandığı anahtarı geçersiz kılar.

Komut satırında derleme yaparsanız, derlemenizi imzalamak için bağlayıcı seçeneklerini kullanın ve sonra işlem sonrası bir araç (mt.exe gibi) çalıştırırsanız, derlemeyi sn.exe ile yeniden imzalamanız gerekir. Alternatif olarak, derlemeyi oluşturup imzalamayı erteleyebilir ve işlem sonrası araçları çalıştırdıktan sonra imzalamayı tamamlayabilirsiniz.

Geliştirme ortamında oluştururken imzalama özniteliklerini kullanırsanız, derleme sonrası bir olayda sn.exe ([Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)) açıkça çağırarak derlemeyi başarıyla imzalayabilirsiniz. Daha fazla bilgi için bkz. [derleme olaylarını belirtme](../build/specifying-build-events.md). Öznitelikleri ve derleme sonrası olayını kullanıyorsanız, bağlayıcı seçenekleri kullanmaya kıyasla derleme süreleri daha az olabilir.

Aşağıdaki bağlayıcı seçenekleri derleme imzalamayı destekler:

- [/DELAYSIGN (bir derlemeyi kısmen Imzala)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (bir derlemeyi Imzalamak için anahtar veya anahtar çiftini belirt)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (bir derlemeyi Imzalamak için bir anahtar kapsayıcısı belirtin)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Güçlü derlemeler hakkında daha fazla bilgi için bkz. [Strong-Named derlemeleri oluşturma ve kullanma](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
