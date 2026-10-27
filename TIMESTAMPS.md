# OpenTimestamps attestations

Each `.ots` file in `ots/` is a complete OpenTimestamps proof (upgraded 2026-10-27) that the SHA-256 digest below existed before the stated Bitcoin block. Verify with `ots verify ots/<name>.ots -f <file>` (needs a Bitcoin node) or inspect with `ots info`. Block times are the block header times (UTC), looked up on blockstream.info.

| Earliest block | Block time | Proof file | SHA-256 | Covers |
|---|---|---|---|---|
| 952131 | 2026-06-02 16:46 UTC | `langlands_millennium.patch.ots` | `ebaceb9a5e05fb0d…` | langlands_millennium.patch |
| 952138 | 2026-06-02 18:27 UTC | `langlands_millennium.patch(1).ots` | `124b67bde57f2980…` | langlands_millennium.patch(1) |
| 952310 | 2026-06-04 08:21 UTC | `HSLN.lean.ots` | `d02a02e395ca18ed…` | lean.zip → lean/HSLN.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNAlgebra.lean.ots` | `2b1ac6eb7710915c…` | lean.zip → lean/HSLNAlgebra.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNBSD.lean.ots` | `eb46638800c2ea04…` | lean.zip → lean/HSLNBSD.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNBridge.lean.ots` | `a6be8dc3b5878a01…` | lean.zip → lean/HSLNBridge.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNComplexity.lean.ots` | `6b6e68e053c3b166…` | lean.zip → lean/HSLNComplexity.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNDivisorEuler.lean.ots` | `bdaeb77be1c5efaa…` | lean.zip → lean/HSLNDivisorEuler.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNFactor.lean.ots` | `de3bdbcb123a2304…` | lean.zip → lean/HSLNFactor.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNFrontier.lean.ots` | `65b29ef96d277c25…` | lean.zip → lean/HSLNFrontier.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNHecke.lean.ots` | `bc2513bc11fa4e4d…` | lean.zip → lean/HSLNHecke.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNHilbertPolya.lean.ots` | `7ebc69f97e8215e4…` | lean.zip → lean/HSLNHilbertPolya.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNHodge.lean.ots` | `de4b950099c96173…` | lean.zip → lean/HSLNHodge.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNKTheory.lean.ots` | `26749bf6611f8e62…` | lean.zip → lean/HSLNKTheory.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNLFunctions.lean.ots` | `314a51cc24d4a264…` | lean.zip → lean/HSLNLFunctions.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNLanglands.lean.ots` | `06a133af3b425e0b…` | lean.zip → lean/HSLNLanglands.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNQuantumState.lean.ots` | `3fa976c7added96b…` | lean.zip → lean/HSLNQuantumState.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNRH.lean.ots` | `8dea834f05d37128…` | lean.zip → lean/HSLNRH.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNSerre.lean.ots` | `403e9d0bc1dfb517…` | lean.zip → lean/HSLNSerre.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNSpectral.lean.ots` | `3de71958dcaf9e45…` | lean.zip → lean/HSLNSpectral.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNStructureNotSearch.lean.ots` | `d599b52573d6fae7…` | lean.zip → lean/HSLNStructureNotSearch.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNTraceFormula.lean.ots` | `80b185a4985b366d…` | lean.zip → lean/HSLNTraceFormula.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNVerify.lean.ots` | `106e659be5a9be99…` | lean.zip → lean/HSLNVerify.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNWeilPositivity.lean.ots` | `6b9fc1eaba3f4d97…` | lean.zip → lean/HSLNWeilPositivity.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNYangMills.lean.ots` | `cbbcf8d2e5b832f6…` | lean.zip → lean/HSLNYangMills.lean |
| 952310 | 2026-06-04 08:21 UTC | `HSLNZeta.lean.ots` | `0fdc6421e957ee6e…` | lean.zip → lean/HSLNZeta.lean |
| 952310 | 2026-06-04 08:21 UTC | `SpectralArithmetic.lean.ots` | `284083038a4b7f86…` | lean.zip → lean/SpectralArithmetic.lean |
| 952310 | 2026-06-04 08:21 UTC | `SpectralBosonFermion.lean.ots` | `68a5ebc1fee83d63…` | lean.zip → lean/SpectralBosonFermion.lean |
| 952310 | 2026-06-04 08:21 UTC | `SpectralShor.lean.ots` | `b9b199b7a4ddde67…` | lean.zip → lean/SpectralShor.lean |
| 952310 | 2026-06-04 08:21 UTC | `SpectralTorsion.lean.ots` | `758883ffd1309d49…` | lean.zip → lean/SpectralTorsion.lean |
| 952310 | 2026-06-04 08:21 UTC | `langlands_program.patch.ots` | `124b67bde57f2980…` | langlands_program.patch |
| 952310 | 2026-06-04 08:21 UTC | `langlands_program.patch(1).ots` | `124b67bde57f2980…` | langlands_program.patch(1) |
| 952310 | 2026-06-04 08:21 UTC | `math-connections.md.ots` | `5335265d6469a61c…` | docs.zip → docs/math-connections.md |
| 952310 | 2026-06-04 08:21 UTC | `system-spec.md.ots` | `0eea1cb47f0acc0a…` | docs.zip → docs/system-spec.md |
| 952310 | 2026-06-04 08:21 UTC | `visualizations_part1.zip.ots` | `f08c873a28c3cd1d…` | visualizations_part1.zip |
| 952310 | 2026-06-04 08:21 UTC | `visualizations_part2.zip.ots` | `5aa8f962cafd69b0…` | visualizations_part2.zip |
