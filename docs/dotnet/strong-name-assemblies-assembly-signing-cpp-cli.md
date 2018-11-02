---
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
ms.openlocfilehash: c23c3b70a2152fbceb771e085b73d7daf7aa3c2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527562"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)

Bu konuda, genellikle derlemenizin güçlü bir isim verilmesi olarak adlandırılan derlemenizi nasıl oturum anlatılmaktadır.

## <a name="remarks"></a>Açıklamalar

Visual C++ kullanırken, derleme imzalama için CLR öznitelikleri için ilgili sorunlardan kaçınmak için bir derlemeyi imzalamak için bağlayıcı seçenekleri kullanın:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Anahtar adı, dosya adı, gizli bilgileri içeriyorsa, bir güvenlik riski olabilecek derleme metaverisine yerleştirilmez görünür hale öznitelikleri kullanmayan nedenleri içerir. Ayrıca, Visual C++ geliştirme ortamı tarafından kullanılan yapı işleminin bir derlemeyi bir katı ad vermek için CLR öznitelikleri kullanın ve ardından derleme üzerinde mt.exe gibi işlem sonrası bir araç çalıştırın, derleme imzalanır anahtarı geçersiz kılar.

Komut satırında derleme, bağlayıcı seçenekleri, derlemeyi imzalamak için kullanın ve ardından bir işlem sonrası Aracı (mt.exe gibi) çalıştırın, derleme sn.exe ile yeniden imzalamanız gerekecektir. Alternatif olarak, derleyebilir ve derleme oturum gecikme ve işlem sonrası araçları çalıştırdıktan sonra imzalama tamamlayın.

Geliştirme ortamında oluştururken imzalama öznitelikler kullanıyorsa, başarıyla derleme açıkça sn.exe çağırarak oturum ([Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)) derleme sonrası olay. Daha fazla bilgi için [derleme olayları belirtme](../ide/specifying-build-events.md). Öznitelikler ve bağlayıcı seçenekleri kullanmaya kıyasla bir derleme sonrası olay kullanıyorsanız derleme zamanlarını daha az olabilir.

Derleme imzalama aşağıdaki bağlayıcı seçenekleri destekler:

- [/DELAYSIGN (Derlemeyi Kısmen İmzala)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Tanımlayıcı derlemeler hakkında daha fazla bilgi için bkz. [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)