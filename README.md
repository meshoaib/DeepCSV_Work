# DeepCSV_Work
#Copying files from another Package

#https://github.com/CMSDeepFlavour/DeepNTuples

#NTuple framework for DeepFlavour 

# Installation (CMSSW 8_4_X and 9_0_X)

cmsrel CMSSW_8_0_25

cd CMSSW_8_0_25/src/

cmsenv

git cms-init

git clone https://github.com/CMSDeepFlavour/DeepNTuples

# Add JetToolBox

cd DeepNTuples

git submodule init

git submodule update

#DeepCSV is already in the release, but with different names, which will become the defaults in the close future

sed -i 's|deepFlavourJetTags|pfDeepCSVJetTags|g' DeepNTuples/DeepNtuplizer/production/DeepNtuplizer.py

#compile

scram b -j 4
